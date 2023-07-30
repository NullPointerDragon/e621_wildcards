# e621_wildcards

This project contains Wildcard files with tags related to e621-trained SD models.

Files prefixed by "e621" are fully compatible with e621-trained models (all can be founds as tags in e621).
Files with "enriched" on their names were augmented with ChatGPT.
Most full outfits are in the "outfits" folder now.

Full list of wildcard files:
	cultural_adjectives
	cultural_outfits
	e621_all_artists_above_100
	e621_all_species_above_100
	e621_all_tags_above_100
	e621_angles
	e621_close_up
	e621_clothing
	e621_colors
	e621_expressions
	e621_fat_traits
	e621_figures
	e621_figures_fat
	e621_first_person_pov
	e621_framing
	e621_genders
	e621_hair_colors
	e621_hair_styles
	e621_hair_traits
	e621_hair_traits_common
	e621_holding_objects
	e621_locations
	e621_muscular_traits
	e621_outfit_colors
	e621_outfits
	e621_poses
	species_enriched_nonmedia_500
	species_enriched_nonmedia_nonhuman_500
	species_enriched_top1000
	species_enriched_top1000_no_mon
	e621_outfits
	outfits/outfits_cultural_enriched
	outfits/outfits_fancy_enriched_female
	outfits/outfits_fancy_enriched_male
	outfits/outfits_medieval
	outfits/outfits_medieval_enriched
	outfits/outfits_middle_eastern
	outfits/outfits_modern_enriched
	outfits/outfits_modern_enriched_female
	outfits/outfits_modern_enriched_male
	outfits/outfits_modern_enriched2
	outfits/outfits_oriental


## Installation

1) Install SD Dynamic Prompts: https://github.com/adieyal/sd-dynamic-prompts
2) Paste the selected wildcards files at stable-diffusion-webui\extensions\sd-dynamic-prompts\wildcards (or change the path on your configs)
3) Use {__nameOfTheWildcardsFile__} in your prompt (between "{__ __}") to randomly and dynamically pick a value from them
4) More instructions can be found in the SD Dynamic Prompts page

## Usage

Here's an example of prompt that generates anthros with 5-20 random tags, in a random detailed location, with a random angle and framing, with 1~10 clothing items, a random pose and 6 random artists:

	(anthro)

	(hi res, best quality, high quality, detailed:1.2)

	{5-20$$__e621_all_tags_above_100__}

	({__e621_locations__}, detailed background:1.2)

	{__e621_angles__}
	{__e621_framing__}

	(clothing, {1-10$$__e621_clothing__})

	({__e621_poses__})

	({6$$__e621_all_artists_above_100__}:1.3)
	
The next one generates a random species, gender, body figure, location and outfit, with the possibility of a random angle, framing, pose and expression as well:

	anthro, {__e621_figures__} ({__e621_genders__}:1.2), ({__species_enriched_nonmedia_nonhuman_500__}:1.3), {{__e621_colors__} body| }

	{{__e621_hair_colors__}| }, {{__e621_hair_styles__}| }, {{__e621_hair_traits_common__}| }

	{0-1$$__e621_angles__}, {0-1$$__e621_framing__}, {0-1$$__e621_poses__}, {0-1$$__e621_expressions__}

	{{__cultural_adjectives__}| } {__e621_locations__} background, detailed background

	(clothing, {__outfits/*__}:1.1), {__e621_outfit_colors__}
