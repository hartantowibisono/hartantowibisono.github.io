<html>
	<header>	
		<meta name="viewport" content="width=device-width, initial-scale=1, minimum-scale=1">
	</header>
	<body>
		<div class="body1">
			Hello
		</div>
		<style type='text/css'>
	.embeddedServiceHelpButton .helpButton .uiButton {
		background-color: #21ED8B;
		font-family: "Helvetica", sans-serif;
	}
	.embeddedServiceHelpButton .helpButton .uiButton:focus {
		outline: 1px solid #21ED8B;
	}
</style>

<script type='text/javascript' src='https://service.force.com/embeddedservice/5.0/esw.min.js'></script>
<script type='text/javascript'>
	var initESW = function(gslbBaseURL) {
		embedded_svc.settings.displayHelpButton = true; //Or false
		embedded_svc.settings.language = ''; //For example, enter 'en' or 'en-US'

		//embedded_svc.settings.defaultMinimizedText = '...'; //(Defaults to Chat with an Expert)
		//embedded_svc.settings.disabledMinimizedText = '...'; //(Defaults to Agent Offline)

		//embedded_svc.settings.loadingText = ''; //(Defaults to Loading)
		//embedded_svc.settings.storageDomain = 'yourdomain.com'; //(Sets the domain for your deployment so that visitors can navigate subdomains during a chat session)

		// Settings for Chat
		//embedded_svc.settings.directToButtonRouting = function(prechatFormData) {
			// Dynamically changes the button ID based on what the visitor enters in the pre-chat form.
			// Returns a valid button ID.
		//};
		//embedded_svc.settings.prepopulatedPrechatFields = {}; //Sets the auto-population of pre-chat form fields
		//embedded_svc.settings.fallbackRouting = []; //An array of button IDs, user IDs, or userId_buttonId
		//embedded_svc.settings.offlineSupportMinimizedText = '...'; //(Defaults to Contact Us)

		embedded_svc.settings.enabledFeatures = ['LiveAgent'];
		embedded_svc.settings.entryFeature = 'LiveAgent';

		embedded_svc.init(
			'https://cunning-bear-snzeo3-dev-ed.my.salesforce.com',
			'https://cunning-bear-snzeo3-dev-ed.my.site.com/testhelpcenter',
			gslbBaseURL,
			'00D5i00000AeOsE',
			'Chat_Team_1',
			{
				baseLiveAgentContentURL: 'https://c.la2-c2-hnd.salesforceliveagent.com/content',
				deploymentId: '5725i000000p5gj',
				buttonId: '5735i000000YK8H',
				baseLiveAgentURL: 'https://d.la2-c2-hnd.salesforceliveagent.com/chat',
				eswLiveAgentDevName: 'Chat_Team_1',
				isOfflineSupportEnabled: false
			}
		);
	};

	if (!window.embedded_svc) {
		var s = document.createElement('script');
		s.setAttribute('src', 'https://cunning-bear-snzeo3-dev-ed.my.salesforce.com/embeddedservice/5.0/esw.min.js');
		s.onload = function() {
			initESW(null);
		};
		document.body.appendChild(s);
	} else {
		initESW('https://service.force.com');
	}
</script>
	</body>
</html>
