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

	{5-20$$__misc/e621/all_tags*__}

	({__locations/e621/*__}, detailed background:1.2)

	{__composition/e621/angles*__}
	{__composition/e621/framing*__}

	(clothing, {1-10$$__clothing/e621/*__})

	({__actions/e621/*__})

	({6$$__artists/e621/*__}:1.3)
	
The next one generates a random species, gender, body figure, location and outfit, with the possibility of a random angle, framing, pose and expression as well:

	anthro, {__body/e621/figures*__} ({__body/e621/genders*__}:1.2), ({__species/detailed/nonmedia_nonhuman_500__}:1.3), {{__colors/e621/*__} body| }

	{{__hair/e621/colors*__}| }, {{__hair/e621/styles*__}| }, {{__hair/e621/traits_common*__}| }

	{0-1$$__composition/e621/angles*__}, {0-1$$__composition/e621/framing*__}, {0-1$$__actions/e621/poses*__}, {0-1$$__actions/e621/expressions*__}

	{{__misc/cultural_adjectives__}| } {__locations/*__} background, detailed background

	(clothing, {__outfits/*__}:1.1), {__colors/*__}
	
And the following one uses detailed descriptors for fantasy characters (replace 'fantasy' with 'modern' or 'fancy' for other settings)

	anthro, {__body/e621/figures*__} ({__body/e621/genders*__}:1.2), ({__species/detailed/nonmedia_nonhuman_500__}:1.3), {{__colors/e621/*__} body| }

	{{__hair/e621/colors*__}| }, {{__hair/e621/styles*__}| }, {{__hair/e621/traits_common*__}| }

	{0-1$$__composition/e621/angles*__}, {0-1$$__composition/e621/framing*__}, {0-1$$__actions/e621/poses*__}, {0-1$$__actions/e621/expressions*__}

	{__locations/detailed/fantasy*__} background, detailed background

	(clothing, {__outfits/detailed/fantasy*__}:1.1), {__colors/*__}
