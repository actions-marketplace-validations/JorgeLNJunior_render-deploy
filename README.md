<div align="center" id="short-description-and-logo">

  <!-- Logo -->
  <!-- <img src="https://ps.w.org/wp-githuber-md/assets/icon-256x256.png?rev=2194656" width="200px">  -->

  <!-- Título -->
  <h1>Render Deploy</h1>

  Deploy your [Render](https://render.com) app through GitHub Actions.

</div>

<!-- Badges -->
<div align="center" id="badges">

[![CI](https://img.shields.io/github/actions/workflow/status/JorgeLNJunior/render-deploy/ci.yml?branch=main)](https://github.com/JorgeLNJunior/render-deploy/actions/workflows/ci.yml)
[![Coverage Status](https://coveralls.io/repos/github/JorgeLNJunior/render-deploy/badge.svg?branch=main)](https://coveralls.io/github/JorgeLNJunior/render-deploy?branch=main)
[![License](https://img.shields.io/github/license/JorgeLNJunior/render-deploy?color=lgreen)](LICENSE)

</div>

## Usage

- First you need to disable auto deploy option in your render app settings. `Settings > Build and Deploy > Auto-Deploy`. 
- Add your `service id` and your render `api key` to your GitHub repository secrets. `Settings > Secrets > Actions`.
- Add this action to your pipeline.

```yml
steps:
    - uses: actions/checkout@v3
    - uses: JorgeLNJunior/render-deploy@v1.3.2
      with:
        service_id: ${{ secrets.RENDER_SERVICE_ID }} # required
        api_key: ${{ secrets.RENDER_API_KEY }} # required
        clear_cache: false # Clear build cache. Optional
        wait_deploy: false # Wait until the deploy status is successful. Warning! Free Render services can take +5 minutes to be fully deployed. Optional
```

## Licence

Project under [MIT »](/LICENSE) license.
