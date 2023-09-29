## {{page-title}}

1. Software assets to be held on [GitHub](https://github.com/nhsconnect){:target="_blank"}.
1. Software to be licensed under the [Apache 2 license](http://www.apache.org/licenses/LICENSE-2.0){:target="_blank"}.
1. Code repositories will use the [GitFlow](http://nvie.com/posts/a-successful-git-branching-model/){:target="_blank"} branching model.
	a. Contributors make changes by submitting [pull requests](https://help.github.com/articles/using-pull-requests/){:target="_blank"}.
	a. Editors review pull requests for consistency prior to merging into develop.
	a. Periodically, editors create a release candidate (where appropriate, editors will seek wider review of release candidate assets including clinical review, Connectathon testing and so on).
	a. Following successful review, assets are marked as active and published to master branch. 
1. Software assets will follow [Semantic Versioning](http://semver.org/){:target="_blank"}.
	a. Major versions will be maintained in parallel for a period of time before deprecation.
1. GitHub [webhooks](https://developer.github.com/webhooks/){:target="_blank"} will be used to automatically build and publish software assets to a public test instance.
