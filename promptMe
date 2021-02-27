// promptMe - a roam/JS prompt to generate evergreen notes from different important tags in your graph.
// 2.7.21
// code snippets + insights here from many, including David Bieber, https://github.com/jacrify/, and a countless number of others.
// this is a working model similar to some of roamhacker's SmartBlocks. 
// 

// find first page reference. insert page title in quotes.
let referencesWriting = window.roamAlphaAPI.q(`[
    :find ?text
    :in $ ?title
    :where
    [?page :node/title ?title]
    [?e :block/refs ?page]
    [?e :block/string ?text]
  ]`, 'writing');

// randomize result from page
	randomWriting = referencesWriting[Math.floor(Math.random() * referencesWriting.length)]
  
// find second page reference. insert page title in quotes.
let referencesIdeas = window.roamAlphaAPI.q(`[
    :find ?text
    :in $ ?title
    :where
    [?page :node/title ?title]
    [?e :block/refs ?page]
    [?e :block/string ?text]
  ]`, 'My Best Ideas');

// randomize result from page
	randomIdea = referencesIdeas[Math.floor(Math.random() * referencesIdeas.length)]
	
// generate prompt on page when run
	var evergreenPrompt = prompt(randomWriting + "\n" + randomIdea + "\n" + "Match up: What does this idea + an old writing topic make you think?")

// store response with tags in a date page. edit if you have a target UID to store.
if (evergreenPrompt != null) {
          window
          .roamAlphaAPI
          .createBlock(
          {"location": 
            {"parent-uid": "02-09-2021", 
            "order": 0}, 
          "block": 
                {"string": "[[prompt me]] - " + evergreenPrompt + "\n" + randomWriting + "\n" + randomIdea}});
}
