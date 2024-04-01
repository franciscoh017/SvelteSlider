<swiper-container
  pagination={false}
  class="affiliates-swiper"
  space-between={15}
  slides-per-view={2}
  centered-slides
>
  {#each executives as exectutive}
  <swiper-slide>
    <div class="exec-slide">
      <p class="active-exec-slide-header" align="center">
        { exectutive.position }
      </p>
      <p class="inactive-exec-slide-header" align="center">
        { exectutive.position }
      </p>
      <img class="exec-photo" alt="" src={exectutive.photo}>
      <Block class="active-exec-details">
        <p class="exec-name" align="center">{exectutive.name}</p>
        <small class="exec-position">{exectutive.positionDescription}</small>
      </Block>
      <Block class="inactive-exec-details">
        <p class="exec-name"></p>
        <small class="exec-position"></small>
      </Block>
    </div>
  </swiper-slide>
  {/each}
</swiper-container>

<script>
  import { Block } from 'framework7-svelte';

  export let selected;


  $: currentAffiliate = formatAffiliate(selected);
  $: executives = currentAffiliate.executives;

  function formatAffiliate(affiliate) {
    // Extracting affiliate name
    const name = affiliate.affiliateName;

    // Extracting executives information
    const executives = [];
    affiliate?.executives?.forEach(executiveGroup => {
        executiveGroup.positions.profiles.forEach(profile => {
            const executive = {
                name: profile.name,
                position: executiveGroup.positions.positionName,
                positionDescription: profile.positionDescription,
                photo: profile.photo
            };
            executives.push(executive);
        });
    });

    console.log(selected, executives);
    return { name, executives };
  }
</script>