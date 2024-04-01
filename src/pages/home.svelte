<script>
  import {
    Page,
    Navbar,
    NavLeft,
    NavTitle,
    NavTitleLarge,
    NavRight,
    Link,
  } from 'framework7-svelte';

  import AffiliatesSwiper from '../components/affiliates-swiper.svelte';

  const affiliatesData = [
  {
    affiliateName: "Affiliate 1",
    executives: [
      {
        positions: {
          positionName: "President",
          profiles: [
            {
              name: "John Doe",
              positionDescription: "President",
              photo: "https://i0.wp.com/digitalhealthskills.com/wp-content/uploads/2022/11/3da39-no-user-image-icon-27.png?fit=500%2C500&ssl=1DA4C0DB65FD16383AC641872B28894A983589"
            }
          ]
        }
      },
      {
        positions: {
          positionName: "Senior Executive Vice Presidents",
          profiles: [
            {
              name: "Jane Doe",
              positionDescription: "Senior Executive Vice President of Technology and Operations",
              photo: "https://i0.wp.com/digitalhealthskills.com/wp-content/uploads/2022/11/3da39-no-user-image-icon-27.png?fit=500%2C500&ssl=1DA4BFDB65FD163838AF06D5029E2B51694753"
            },
            {
              name: "Alice Smith",
              positionDescription: "Senior Executive Vice President of National and International Business",
              photo: "https://i0.wp.com/digitalhealthskills.com/wp-content/uploads/2022/11/3da39-no-user-image-icon-27.png?fit=500%2C500&ssl=1DA4BEDB65FD16382071760ED296CE659FA152"
            },
            {
              name: "Bob Johnson",
              positionDescription: "Senior Executive Vice President of Human Resources, Cultural Transformation, Credit Management, and Compliance",
              photo: "https://i0.wp.com/digitalhealthskills.com/wp-content/uploads/2022/11/3da39-no-user-image-icon-27.png?fit=500%2C500&ssl=1DA4BFDB65FD16381DA81CFB702DAAC538F09C"
            }
          ]
        }
      },
      // Add more executives as needed
    ]
  },
  // Add more affiliates as needed
];


  const selectedAffiliate = affiliatesData[0];
</script>

<Page name="home">
  <!-- Top Navbar -->
  <Navbar large sliding={false}>
    <NavLeft>
      <Link iconIos="f7:menu" iconMd="material:menu" panelOpen="left" />
    </NavLeft>
    <NavTitle sliding>Swiper</NavTitle>
    <NavRight>
      <Link iconIos="f7:menu" iconMd="material:menu" panelOpen="right" />
    </NavRight>
    <NavTitleLarge>Slider</NavTitleLarge>
  </Navbar>
  <!-- Page content -->

  <br>

  <section>
    <AffiliatesSwiper selected={selectedAffiliate}/>
  </section>
</Page>
