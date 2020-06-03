# Boxalino Real Time User Experience (RTUX) Integration - Shopware6

## Introduction
This repository is to be used as a sample on how to integrate and define desired Boxalino features.
The integration is managed by the client.
Boxalino can provide further documentation and assistance upon request.

Included functionalities (with samples of templates):
1. Autocomplete integration
2. Search integration
3. PDP recommendations (via subscriber event)
4. Navigation
5. CMS element for Boxalino Narrative block
6. Basket recommendations*

The repository is being updated with new guidelines & scenario.

## Integration
Generally, this repository is not subject to Boxalino maintenance on client setup.
This means, the guidelines are meant to be integrated in a repository/plugin maintainted&developed by the client`s team.

This repository can be deployed for testing Boxalino features or in order to prepare your own integration.
In order to deploy it, check the *Setup* steps bellow.

## Setup
1. Add the plugin to your project via composer
``composer require boxalino/rtux-integration-shopware``

2. Activate the plugin per Shopware use
``./bin/console plugin:refresh``
``./bin/console plugin:install --activate --clearCache BoxalinoRealTimeUserExperienceIntegration``
  
3. Import the content of the complete-guidelines (https://github.com/boxalino/rtux-integration-shopware/tree/master/doc/complete-guidelines) JSONs in Boxalino Intelligence Admin; test, save & publish.
    * Layout Blocks (Boxalino Intelligence Admin >> Marketing >> Layout Blocks)
    * Template Resources (Boxalino Intelligence Admin >> Advanced >> Template Resources)
    * Narratives  (Boxalino Intelligence Admin >> Marketing >> Narratives)

4. Search, autocomplete, cross-sellings will work automatically. 
In order to have navigation active, read the #About section in the cms-navigation documentation.
In order to add sliders on home-page/other segments, read the #About section in the cms-slider documentation.

## Documentation

The latest documentation is available upon request.

## Contact us!

If you have any question, just contact us at support@boxalino.com

*the marked features are not yet available
