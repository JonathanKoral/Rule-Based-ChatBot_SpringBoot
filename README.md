# Rule-Based-ChatBot_SpringBoot


Are you ready to build a chatbot? In this lab, you will create a simple rule-based chatbot using Spring Boot and a web-based interface. The web-based interface allows you to communicate with the rule-based chatbot over a network using a browser. For this project, you will target only the desktop browser. The chatbot will be able to answer the following questions for countries across the world:

the country’s capital

its national animal, and

its national flower.

The chatbot will possess the basic intelligence to remember a conversation, like which country you select, and continue with that country to provide more details, which is achieved by session management. You will be using Amazon Q Developer within IntelliJ IDE to leverage the power of GenAI to code some of the critical or missing parts of the starter code. By analyzing the prompts, you will gain valuable insights into how prompts must be designed.

This project supports your understanding of practical coding with Amazon Q Developer, a GenAI-powered coding assistant, and session management. Leveraging Amazon Q Developer to complete tasks will enhance your skills in prompt design and efficient development workflows. 

Goal

Your goal is to create a Spring Boot rule-based chatbot that:

has the capability to chat within parameters and return results

has the capability to provide information about a country’s capital and national animal and flower 

has the ability to remember which country has been selected during a chat for further information and

will provide a web-based interface for the user to interact with the rule-based chatbot engine via any modern desktop browser.

🖥️  Note: When you encounter this icon, it’s time to get into your IDE and start coding!

In your lab environment, open IntelliJ by double-clicking on the icon.


Before you start, ensure that:

Amazon Q Developer is integrated with your IntelliJ IDEA with the Amazon Q Developer plugin

the Amazon Q Developer plugin is enabled and in a running state

Amazon Q Developer plugin has its auto-suggestions feature turned on, and the auto-suggestion feature is not paused.

In addition, make sure that you are familiar with prompting the Amazon Q Developer AI within IntelliJ and have completed all prerequisite items, including readings, videos, and labs. This includes the final lab titled Creating a recommendation program in Module 2, Lesson 2. 

About the starter code: 

The starter code is arranged as follows:

The core or base package is com.ajsd.chatbot.

The packages and classes inside the core or base package are:

The package for the model classes is com.ajsd.chatbot.model, and it contains: 

ConversationContext, which is used to store the current step of communication, selected countries being discussed, and available options. 

CountryInfo, which is used to store information about a country. It is used to associate a country's name with the capital, nationalAnimal, and nationalFlower.

The package for configuration classes is com.ajsd.chatbot.config, and it contains:

CountryDataLoader, which is used to load the information about the countries from the JSON file named countries_data.json in the resources folder of the Spring Boot application. This class also provides methods to access data that is used by the service, storing the data in a HashMap.

The package for the service classes is com.ajsd.chatbot.service, and it contains: 

ChatbotService, which utilizes the CountryDataLoader class to access the data of the different countries and provides access to the data via this Service class. 

RuleBasedEngine is the class at the heart of the rules of the Chatbot. It contains the logic to return the appropriate response to the user and remembers the context by leveraging the ConversationContext class object, which is passed to it by the controller. 

The package for the controller classes is com.ajsd.chatbot.controller, and it contains: 

HomeController, a controller class with only one endpoint “/,” returns the thymeleaf template index.html.

ChatbotController, which is the controller responsible for all the communication between the web-based interface and the RuleBasedEngine class. It utilizes a session-based reference to an object of the ConversationContext class so that each session communication, like the country being discussed, is remembered. This controller class has a single endpoint, “/chat,” responding to the HTTP verb type POST.  

The class inside the core or base package is ChatbotApplication, which is the starting point containing the main method of the Spring Boot Application.

You can review the following image for a breakdown of the folders. 


The resources folder contains:

The application.properties file is used to configure Spring Boot properties. 

A templates folder that contains the file index.html. 

A JSON file named countries_data.json contains the data for the countries – its capital, national animal, and national flower – in JSON format. 

A folder named internal_image_for_ai contains an image file named layout_for_chatbot.png. This file will not be used but is a reference for you to understand what the layout will look like. You will describe the layout to Amazon Q Developer so that GenAI can generate the layout and functionality. Having the image will let you understand how an image layout is described in a prompt for GenAI.

Here is the image, also known as a wireframe diagram. You will use a text prompt that describes this layout and its functionality.
