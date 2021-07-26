# qa-tools-repo

<a href="https://emoji.gg/emoji/5498_catJAM"><img src="https://emoji.gg/assets/emoji/5498_catJAM.gif" width="64px" height="64px" alt="catJAM"></a>*Repository to my QA tools, snippets and demo projects.* <a href="https://emoji.gg/emoji/1430_catJAMReversed"><img src="https://emoji.gg/assets/emoji/1430_catJAMReversed.gif" width="64px" height="64px" alt="catJAMReversed"></a>

**Artillery.io**
Fast and simple load/stress tests, for more infos https://artillery.io/docs/
Example:

    config:
	    target: "https://localhost:3000"
	    phases:
		    - duration: 30
			  arrivalRate: 1
			  rampTo: 50
    scenarios:
	    - flow:
		    - get:
			    url: "/teste/de/exemplo/231231-51464-faef1451"
