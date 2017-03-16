# faebook_data-_craping
facebook data scraping using requests and json in python 3

"""
Created on Thu Mar 16 22:57:19 2017

@author: pandurang
"""

import json
import requests

def create_url(base_url, APP_ID, APP_SECRET,user_name):
    #method to return 
    args_ = '/' +user_name +'/posts/?key=value&access_token='+ APP_ID +'|'+ APP_SECRET
    final_url = base_url + args_
    return final_url

#Login to the facebook developers page and get your APP_ID and APP_SECRET
APP_ID=app_id
APP_SECRET=app_secret
#User name is the name of facebook account from which you want to scrape the data
user_name=any_
fb_url='https://graph.facebook.com'
res_url = create_url(fb_url, APP_ID, APP_SECRET,user_name)
fb_response = requests.get(res_url)
json_posts =json.loads(fb_response.text)
json_fbposts = json_posts['data']
print(json_fbposts) 
