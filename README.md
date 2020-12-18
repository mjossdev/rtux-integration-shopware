# Boxalino Real Time User Experience (RTUX) Integration - Shopware6

## Introduction
This repository is provided as guidelines (tutorials) on how to integrate and define desired Boxalino features.
The integration is managed by the client.
Boxalino can provide further documentation and assistance upon request.

Included functionalities (with samples of templates):
1. Autocomplete integration
2. JS autocomplete integration (faster)
3. Search integration
4. PDP recommendations (via subscriber event)
5. Navigation
6. CMS element for Boxalino Narrative block
7. Dynamic router (ex: for brand pages

The repository is being updated with new guidelines & scenario.
**Check the wiki page for instructions https://github.com/boxalino/rtux-integration-shopware/wiki**

**We value your feedback and we welcome the community`s pull/merge-requests. Thank you.**

## Integration
Generally, this repository is not subject to Boxalino maintenance on client setup.
This means, the guidelines are meant to be integrated (replicated) in a repository/plugin maintainted&developed by the client`s team.

This repository can be deployed for checking out Boxalino features (as a demo).
By requiring this repository, it will also install other dependencies. Please review the [composer.json](https://github.com/boxalino/rtux-integration-shopware/blob/master/composer.json)
and follow-up with other dependencies deployments guidelines.

In order to create your own integration layer with the Boxalino`s assistance - please check the [wiki on Initial Setup (Boxalino Assisted)](https://github.com/boxalino/rtux-integration-shopware/wiki/Initial-Setup-(Boxalino-assisted)).

In order to create your own integration layer - please start in the [wiki](https://github.com/boxalino/rtux-integration-shopware/wiki#before-you-start).

In order to deploy it for local demo (without Boxalino assistance or a need to maintain the code in a client setup), check the *Setup* steps bellow.

## Setup
1. Follow the integration steps for the [data layer](https://github.com/boxalino/exporter-shopware6) and the [framework layer](https://github.com/boxalino/rtux-shopware):
   * ``composer require boxalino/rtux-shopware``
   * ``composer require boxalino/exporter-shopware6``
   * ``./bin/console plugin:refresh``
   * ``./bin/console plugin:install --activate --clearCache BoxalinoExporter BoxalinoRealTimeUserExperience``
   
2. Add the plugin to your project via composer (it will install dependencies [rtux-api-php, rtux-shopware, exporter-shopware6](https://github.com/boxalino/rtux-integration-shopware/blob/master/composer.json))
``composer require boxalino/rtux-integration-shopware``

3. Activate the plugin per Shopware use
``./bin/console plugin:refresh``
``./bin/console plugin:install --activate --clearCache BoxalinoRealTimeUserExperienceIntegration``

4. Due to the JS files in the plugin (for listing & filters), a theme compilation might be required:
``./psh.phar storefront:build`` or ``./bin/build-storefront.sh ``
  
5. Due to the JS files in the dependency plugin (tracker, Shopware6 CMS blocks, etc), a theme compilation might be required:
``./psh.phar administration:build `` or ``./bin/build-administration.sh ``

6. Log in administration panel (<your-site>/admin) and set the configurations for the framework layer and expporter.
``admin#/sw/plugin/settings/BoxalinoRealTimeUserExperience``
``admin#/sw/plugin/settings/BoxalinoExporter``

7. In order to kick off your account, a full export is required. 
More information available https://github.com/boxalino/exporter-shopware6
For this, please set the exporter configuration per Sales Channel and disable the plugin where it is not in use.
The Headless channel must have the plugin disabled.
``./bin/console boxalino:exporter:run full``

8. Import the content of [the complete-guidelines](https://github.com/boxalino/rtux-integration-shopware/tree/master/doc/complete-guidelines) JSONs in Boxalino Intelligence Admin; test, save & publish.
    * Layout Blocks (Boxalino Intelligence Admin >> Marketing >> Layout Blocks)
    * Template Resources (Boxalino Intelligence Admin >> Advanced >> Template Resources)
    * Narratives  (Boxalino Intelligence Admin >> Marketing >> Narratives)

9. Search, autocomplete, cross-sellings will work automatically. 
In order to have navigation active, read the #About section in the cms-navigation documentation.
In order to add sliders on home-page/other segments, read the #About section in the cms-slider documentation.


## Documentation

The latest documentation is available upon request.
More documentation is available on each dependency repository wiki page.

## Contact us!

If you have any question, just contact us at support@boxalino.com
