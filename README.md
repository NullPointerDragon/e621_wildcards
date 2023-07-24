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

	(clothing, clothed, {1-10$$__e621_clothing__})

	({__e621_poses__})

	({6$$__e621_all_artists_above_100__}:1.3)
