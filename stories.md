## complete path 1
* greet
    - utter_greet
* restaurant_search
    - utter_ask_location
* restaurant_search{"location": "Delhi"}
    - slot{"location": "Delhi"}
	- action_check_location
	- slot{"valid_location":"true"}
    - utter_ask_cuisine
* restaurant_search{"cuisine": "chinese"}
    - slot{"cuisine": "chinese"}
    - action_check_cuisine
    - slot{"valid_cuisine": "true"}
    - utter_ask_budget
* restaurant_search{"budget":"Lesser than Rs.300"}
	- slot{"budget":"Lesser than Rs.300"}
	- action_search_restaurants
	- utter_sendmail
* deny
	- utter_goodbye
	- action_restart

## complete path 2
* greet
    - utter_greet
* restaurant_search
    -utter_ask_location
* restaurant_search{"location": "kota"}
    - slot{"location": "kota"}
    - action_check_location
    - slot{"valid_location":"false"}
	- action_reset_location_slot
    - utter_locationNotServices
	- utter_enterOtherLocation
* affirm
	- utter_ask_location
* restaurant_search{"location":"delhi"}
    - slot{"location":"delhi"}
    - action_check_location
    - slot{"valid_location":"true"}
    - utter_ask_cuisine
* restaurant_search{"cuisine": "Mexican"}
    - slot{"cuisine": "Mexican"}
    - action_check_cuisine
    - slot{"valid_cuisine":"true"}
    - utter_ask_budget
* restaurant_search{"budget":"More than 700"}
    - slot{"budget":"More than 700"}
    - action_search_restaurants
    - utter_sendmail
* affirm
    - utter_ask_email
* send_email{"email": "ankurkumar1@gmail.com"}
    - slot{"email": "ankurkumar1@gmail.com"}
    - action_check_emailId
    - slot{"valid_email": "true"}
    - action_send_email
    - utter_sentmail
    - action_restart

## complete path 3
* greet
    - utter_greet
* restaurant_search{"location": "delhi"}
    - slot{"location": "delhi"}
    - action_check_location
    - slot{"valid_location":"true"}
    - utter_ask_cuisine
* restaurant_search{"cuisine": "chinese"}
    - slot{"cuisine": "chinese"}
    - action_check_cuisine
    - slot{"valid_cuisine":"true"}
    - utter_ask_budget
* restaurant_search{"budget":"Lesser than Rs.300"}
    - slot{"budget":"Lesser than Rs.300"}
    - action_search_restaurants
    - utter_sendmail
* affirm
    - utter_ask_email
* send_email{"email": "ankurkumar1@gmail.com"}
    - slot{"email": "ankurkumar1@gmail.com"}
    - action_check_emailId
    - slot{"valid_email": "true"}
    - action_send_email
    - utter_sentmail
    - action_restart


## interactive_story_1
* greet
    - utter_greet
* restaurant_search{"location": "mumbai"}
    - slot{"location": "mumbai"}
    - action_check_location
    - slot{"valid_location":"true"}
    - utter_ask_cuisine
* restaurant_search{"cuisine": "chinese"}
    - slot{"cuisine": "chinese"}
    - action_check_cuisine
    - slot{"valid_cuisine":"true"}
    - utter_ask_budget
* restaurant_search{"budget":"Lesser than Rs.300"}
    - slot{"budget":"Lesser than Rs.300"}
    - action_search_restaurants
	- action_restart
	
## interactive_story_2
* greet
    - utter_greet
* restaurant_search
    - utter_ask_location
* restaurant_search{"location": "Agra", "cuisine": "chinese", "budget": "more than 700"}
    - slot{"budget": "more than 700"}
    - slot{"cuisine": "chinese"}
    - slot{"location": "Agra"}
	- action_check_location
    - slot{"valid_location":"true"}
	- action_check_cuisine
    - slot{"valid_cuisine":"true"}
    - action_search_restaurants
    - utter_sendmail
* deny
	- utter_goodbye
	- action_restart
	
## happy_path
* greet
    - utter_greet
* restaurant_search{"cuisine": "italian", "location": "mumbai","budget":"Rs.300 to 700"}
    - slot{"cuisine": "italian"}
    - slot{"location": "mumbai"}
	- slot{"budget": "Rs.300 to 700"}
	- action_check_location
    - slot{"valid_location":"true"}
	- action_check_cuisine
    - slot{"valid_cuisine":"true"}
    - action_search_restaurants
    - utter_sendmail
* affirm
    - utter_ask_email
* send_email{"email":"deepaksharma.k92@gmail.com"}
    - slot{"email":"deepaksharma.k92@gmail.com"}
    - action_check_emailId
    - slot{"valid_email": "true"}
    - action_send_email
    - utter_sentmail
    - action_restart

## interactive_story_3
* restaurant_search
    - utter_ask_location
* restaurant_search{"location": "Delhi"}
    - slot{"location": "Delhi"}
    - action_check_location
    - slot{"valid_location": "true"}
    - utter_ask_cuisine
* restaurant_search{"cuisine": "American"}
    - slot{"cuisine": "American"}
    - action_check_cuisine
    - slot{"valid_cuisine": "false"}
	- action_reset_cuisine_slot
    - utter_Invalidcuisine
    - utter_ask_cuisine
	- slot{"valid_cuisine": "true"}
    - utter_ask_budget
* restaurant_search{"budget":"Rs.300 to 700"}
    - slot{"budget":"Rs.300 to 700"}
    - action_search_restaurants
	- utter_sendmail
* affirm
    - utter_ask_email
* send_email{"email":"deepaksharma.k92@gmail.com"}
    - slot{"email":"deepaksharma.k92@gmail.com"}
    - action_check_emailId
    - slot{"valid_email": "true"}
    - action_send_email
    - utter_sentmail
    - action_restart

## interactive_story_4
* greet
    - utter_greet
* restaurant_search
    - utter_ask_location
* location{"location": "Agra"}
    - slot{"location": "Agra"}
    - action_check_location
    - slot{"valid_location": "true"}
    - utter_ask_cuisine
* restaurant_search{"cuisine": "South Indian"}
    - slot{"cuisine": "South Indian"}
    - action_check_cuisine
    - slot{"valid_cuisine": "true"}
    - utter_ask_budget
* restaurant_search{"budget": "More than 700"}
    - slot{"budget": "More than 700"}
    - action_search_restaurants
    - utter_sendmail
* deny
    - utter_goodbye
    - action_restart

## interactive_story_5
* restaurant_search
    - utter_ask_location
* location{"location": "rewari"}
    - slot{"location": "rewari"}
    - action_check_location
    - slot{"valid_location": "false"}
	- action_reset_location_slot
    - utter_locationNotServices
    - utter_enterOtherLocation
* deny
    - utter_goodbye
    - action_restart

## interactive_story_6
* Other_than_restaurant_search
    - utter_can_only_search_restaurants
    - utter_want_to_search_restaurants
* affirm
    - utter_ask_location
    - action_check_location
    - slot{"valid_location": "false"}
	- action_reset_location_slot
	- utter_locationNotServices
    - utter_enterOtherLocation
* deny
    - utter_goodbye
    - action_restart
	
## interactive_story_6
* Other_than_restaurant_search
    - utter_can_only_search_restaurants
    - utter_want_to_search_restaurants
* deny
    - utter_goodbye
    - action_restart
	
## interactive_story_7
* greet
    - utter_greet
* restaurant_search
    - utter_ask_location
* location{"location": "Indore"}
    - slot{"location": "Indore"}
    - action_check_location
    - slot{"valid_location": "true"}
    - utter_ask_cuisine
* restaurant_search{"cuisine": "South Indian"}
    - slot{"cuisine": "South Indian"}
    - action_check_cuisine
    - slot{"valid_cuisine": "true"}
    - utter_ask_budget
* restaurant_search{"budget": "More than 700"}
    - slot{"budget": "More than 700"}
    - action_search_restaurants
    - utter_sendmail
* deny
    - utter_goodbye
    - action_restart
	
## interactive_story_8
* restaurant_search{"location": "Indore"}
    - slot{"location": "Indore"}
	- action_check_location
    - slot{"valid_location": "true"}
    - utter_ask_cuisine
* restaurant_search{"cuisine": "chinese"}
    - slot{"cuisine": "chinese"}
    - action_check_cuisine
    - slot{"valid_cuisine": "true"}
    - utter_ask_budget
* restaurant_search{"budget": "Lesser than Rs.300"}
    - slot{"budget": "Lesser than Rs.300"}
    - action_search_restaurants
    - utter_sendmail
* affirm
    - utter_ask_email
* send_email{"email": "ankurkumar1@gmail.com"}
    - slot{"email": "ankurkumar1@gmail.com"}
	- action_check_emailId
	- slot{"valid_email": "true"}
    - action_send_email
    - utter_sentmail
	- action_restart

## interactive_story_9
* restaurant_search{"location": "Meerut"}
    - slot{"location": "Meerut"}
	- action_check_location
    - slot{"valid_location": "true"}
    - utter_ask_cuisine
* restaurant_search{"cuisine": "mexican"}
    - slot{"cuisine": "mexican"}
    - action_check_cuisine
    - slot{"valid_cuisine": "true"}
    - utter_ask_budget
* restaurant_search{"budget": "Rs.300 to 700"}
    - slot{"budget": "Rs.300 to 700"}
    - action_search_restaurants
    - utter_sendmail
* affirm
    - utter_ask_email
* send_email{"email": "ankurkumar1@gmail.com"}
    - slot{"email": "ankurkumar1@gmail.com"}
	- action_check_emailId
	- slot{"valid_email": "false"}
	- action_reset_email_slot
	- utter_email_not_correct
* affirm 
	- utter_ask_email
* send_email{"email": "ankurkumar1@gmail.com"}
    - slot{"email": "ankurkumar1@gmail.com"}
	- action_check_emailId
	- slot{"valid_email": "true"}
    - action_send_email
    - utter_sentmail
	- action_restart
	
## interactive_story_10
* restaurant_search{"cuisine": "chinese", "location": "Indore"}
    - slot{"cuisine": "chinese"}
    - slot{"location": "Indore"}
	- action_check_location
    - slot{"valid_location":"true"}
	- action_check_cuisine
    - slot{"valid_cuisine": "false"}
	- action_reset_cuisine_slot
    - utter_Invalidcuisine
    - utter_ask_cuisine
	- slot{"valid_cuisine": "true"}
    - utter_ask_budget
* restaurant_search{"budget": "Lesser than Rs.300"}
    - slot{"budget": "Lesser than Rs.300"}
    - action_search_restaurants
    - utter_sendmail
* affirm
    - utter_ask_email
* check_email_id
    - action_check_emailId
    - slot{"valid_email": "false"}
	- action_reset_email_slot
    - utter_email_not_correct
* affirm
    - utter_ask_email
* send_email{"email": "ankurkumar1@gmail.com"}
    - slot{"email": "ankurkumar1@gmail.com"}
    - action_check_emailId
    - slot{"valid_email": "true"}
    - action_send_email
    - utter_sentmail
    - action_restart
	
## interactive_story_11
* restaurant_search{"budget": "Rs.300 to 700", "location": "Indore"}
	- slot{"budget": "Rs.300 to 700"}
    - slot{"location": "Indore"}
	- action_check_location
    - slot{"valid_location":"false"}
	- action_reset_location_slot
	- utter_locationNotServices
    - utter_enterOtherLocation
* affirm
	- utter_ask_location
* restaurant_search{"location":"kolkata"}
    - slot{"location":"kolkata"}
    - action_check_location
    - slot{"valid_location":"true"}
    - utter_ask_cuisine
* restaurant_search{"cuisine": "italian"}
    - slot{"cuisine": "italian"}
	- action_check_cuisine
    - slot{"valid_cuisine": "true"}
    - action_search_restaurants
    - utter_sendmail
* affirm
    - utter_ask_email
* check_email_id
    - action_check_emailId
    - slot{"valid_email": "false"}
	- action_reset_email_slot
    - utter_email_not_correct
* affirm
    - utter_ask_email
* send_email{"email": "ankurkumar1@gmail.com"}
    - slot{"email": "ankurkumar1@gmail.com"}
    - action_check_emailId
    - slot{"valid_email": "true"}
    - action_send_email
    - utter_sentmail
    - action_restart
	
## interactive_story_12
* restaurant_search{"budget": "Lesser than Rs.300","cuisine": "italian"}
	- slot{"budget": "Lesser than Rs.300"}
	- slot{"cuisine": "italian"}
	- action_check_cuisine
    - slot{"valid_cuisine": "false"}
	- action_reset_cuisine_slot
    - utter_Invalidcuisine
    - utter_ask_cuisine
	- slot{"valid_cuisine": "false"}
	- action_reset_cuisine_slot
    - utter_Invalidcuisine
    - utter_ask_cuisine
	- slot{"valid_cuisine": "true"}
    - utter_ask_location
* restaurant_search{"location": "Dhanbad"}
    - slot{"location": "Dhanbad"}
	- slot{"valid_location": "false"}
	- action_reset_location_slot
	- utter_locationNotServices
    - utter_enterOtherLocation
* affirm
	- utter_ask_location
* location{"location": "Indore"}
    - slot{"location": "Indore"}
    - action_check_location
    - slot{"valid_location": "true"}
    - action_search_restaurants
    - utter_sendmail
* affirm
    - utter_ask_email
* check_email_id
    - action_check_emailId
    - slot{"valid_email": "false"}
	- action_reset_email_slot
    - utter_email_not_correct
* affirm
    - utter_ask_email
* send_email{"email": "ankurkumar1@gmail.com"}
    - slot{"email": "ankurkumar1@gmail.com"}
    - action_check_emailId
    - slot{"valid_email": "true"}
    - action_send_email
    - utter_sentmail
    - action_restart

## interactive_story_11
* Other_than_restaurant_search
    - utter_can_only_search_restaurants
    - utter_want_to_search_restaurants
* affirm
    - utter_ask_location
* location{"location": "hubli"}
    - slot{"location": "hubli"}
    - utter_locationNotServices
    - utter_enterOtherLocation
* affirm
    - utter_ask_location
* restaurant_search{"location": "pune"}
    - slot{"location": "pune"}
    - action_check_location
    - slot{"valid_location": "true"}
    - utter_ask_cuisine
* Other_than_restaurant_search
    - action_check_cuisine
    - slot{"valid_cuisine": "false"}
	- action_reset_cuisine_slot
    - utter_Invalidcuisine
    - utter_ask_cuisine
* restaurant_search{"cuisine": "North Indian"}
    - slot{"cuisine": "North Indian"}
    - action_check_cuisine
    - slot{"valid_cuisine": "true"}
    - utter_ask_budget
* Other_than_restaurant_search
    - utter_dontunderstand
    - utter_ask_budget
* budget{"budget": "Lesser than Rs.300"}
    - slot{"budget": "Lesser than Rs.300"}
    - action_search_restaurants
    - utter_sendmail
* affirm
    - utter_ask_email
* send_email{"email": "ankurkumar@gmail.com"}
    - slot{"email": "ankurkumar@gmail.com"}
    - action_check_emailId
    - slot{"valid_email": "true"}
    - action_send_email
    - utter_sentmail
    - action_restart

## interactive_story_12
* greet
    - utter_greet
* restaurant_search{"location": "Agra", "cuisine": "chinese", "budget": "More than 700"}
    - slot{"budget": "More than 700"}
    - slot{"cuisine": "chinese"}
    - slot{"location": "Agra"}
    - action_search_restaurants
    - utter_sendmail
* affirm
    - utter_ask_email
* send_email{"email": "ankurkumar1@gmail.com"}
    - slot{"email": "ankurkumar1@gmail.com"}
    - action_check_emailId
    - slot{"valid_email": "true"}
    - action_send_email
    - utter_sentmail
    - action_restart

## interactive_story_13
* greet
    - utter_greet
* restaurant_search{"location": "india"}
    - slot{"location": "india"}
    - action_check_location
    - slot{"valid_location": "false"}
	- action_reset_location_slot
    - utter_locationNotServices
    - utter_enterOtherLocation
* affirm
    - utter_ask_location
* location{"location": "Ahmedabad"}
    - slot{"location": "Ahmedabad"}
    - action_check_location
    - slot{"valid_location": "true"}
    - utter_ask_cuisine
* Other_than_restaurant_search
    - action_check_cuisine
    - slot{"valid_cuisine": "false"}
	- action_reset_cuisine_slot
    - utter_Invalidcuisine
    - utter_ask_cuisine
* Other_than_restaurant_search
    - action_check_cuisine
    - slot{"valid_cuisine": "false"}
	- action_reset_cuisine_slot
    - utter_Invalidcuisine
    - utter_ask_cuisine
* restaurant_search{"cuisine": "North Indian"}
    - slot{"cuisine": "North Indian"}
    - action_check_cuisine
    - slot{"valid_cuisine": "true"}
    - utter_ask_budget
* budget{"budget": "Rs.300 to 700"}
    - slot{"budget": "Rs.300 to 700"}
    - action_search_restaurants
    - utter_sendmail
* deny
    - utter_goodbye
    - action_restart

## interactive_story_14
* restaurant_search{"location": "hydrabad", "cuisine": "chinese"}
    - slot{"cuisine": "chinese"}
    - slot{"location": "hydrabad"}
    - action_check_location
    - slot{"valid_location": "false"}
	- action_reset_location_slot
    - action_check_cuisine
    - slot{"valid_cuisine": "true"}
    - utter_ask_budget
* restaurant_search{"budget": "Rs.300 to 700"}
    - slot{"budget": "Rs.300 to 700"}
    - action_search_restaurants
    - utter_sendmail
* deny
    - utter_goodbye
    - action_restart

## interactive_story_15
* restaurant_search{"location": "Bareilly"}
    - slot{"location": "Bareilly"}
    - action_check_location
    - slot{"valid_location": "true"}
    - utter_ask_cuisine
* restaurant_search{"cuisine": "American"}
    - slot{"cuisine": "American"}
    - action_check_cuisine
    - slot{"valid_cuisine": "true"}
    - utter_ask_budget
* restaurant_search{"budget": "Rs.300 to 700"}
    - slot{"budget": "Rs.300 to 700"}
    - action_search_restaurants
    - utter_sendmail
* affirm
    - utter_ask_email
* send_email{"email": ".test.com"}
    - slot{"email": ".test.com"}
    - action_check_emailId
    - slot{"valid_email": "false"}
	- action_reset_email_slot
    - utter_email_not_correct
* affirm
    - utter_ask_email
* send_email
    - action_check_emailId
    - slot{"valid_email": "false"}
	- action_reset_email_slot
    - utter_email_not_correct
* send_email{"email": "ankur.kumar@ll.com"}
    - slot{"email": "ankur.kumar@ll.com"}
    - action_check_emailId
    - slot{"valid_email": "true"}
    - action_send_email
    - utter_sentmail
    - action_restart

## interactive_story_1
* restaurant_search{"location": "firozabad"}
    - slot{"location": "firozabad"}
    - action_check_location
    - slot{"valid_location": "true"}
    - utter_ask_cuisine
* restaurant_search{"cuisine": "japanese"}
    - slot{"cuisine": "japanese"}
    - action_check_cuisine
    - slot{"valid_cuisine": "false"}
    - action_reset_cuisine_slot
    - utter_Invalidcuisine
    - utter_ask_cuisine
    - action_reset_cuisine_slot
    - slot{"cuisine": null}
* Other_than_restaurant_search
    - utter_ask_cuisine
* location
    - action_check_cuisine
    - slot{"valid_cuisine": "false"}
    - action_reset_cuisine_slot
    - slot{"cuisine": null}
    - utter_Invalidcuisine
    - utter_ask_cuisine
* restaurant_search{"cuisine": "North Indian"}
    - slot{"cuisine": "North Indian"}
    - action_check_cuisine
    - slot{"valid_cuisine": "true"}
    - utter_ask_budget
* restaurant_search{"budget": "Lesser than Rs.300"}
    - slot{"budget": "Lesser than Rs.300"}
    - action_search_restaurants
    - utter_sendmail
* deny
    - utter_goodbye
    - action_restart
