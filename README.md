# e621_wildcards

This project contains Wildcard files with tags related to e621-trained SD models.

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
