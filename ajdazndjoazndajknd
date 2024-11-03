
from selenium import webdriver
from selenium.webdriver import ActionChains
from selenium.webdriver.common.keys import Keys
from selenium.webdriver.common.actions.action_builder import ActionBuilder
import time
from bs4 import BeautifulSoup


# Open Webpage

projects = ['restaurants', 'drug store', 'coffee shop', 'agence','agence location voiture','coiffure','mecanicien','repair telephon','Entreprise de livraison', 'Centre de formation' , 'parapharmacie','Centre de fitness','Services informatiques','patisserie', 'dentist']
countries = ['nabeul', 'dar chaaban', 'somaa', 'tazarka','korba','bani ayshun', 'al-mamurah','béni khiar']
driver = webdriver.Firefox()
driver.get('https://www.google.com/maps/search/Restaurants/@36.4488772,10.7390307,15z/data=!4m9!2m8!3m6!1sRestaurants!2zTmFiZXVs4oCO!3s0x13029895efbdd3d3:0x2e5d60d1569ce4fe!4m2!1d10.7356634!2d36.4512893!6e5?entry=ttu&g_ep=EgoyMDI0MTAyOS4wIKXMDSoASAFQAw%3D%3Dhttps://www.google.com/maps/search/Restaurants/@36.4488772,10.7390307,15z/data=!4m9!2m8!3m6!1sRestaurants!2zTmFiZXVs4oCO!3s0x13029895efbdd3d3:0x2e5d60d1569ce4fe!4m2!1d10.7356634!2d36.4512893!6e5?entry=ttu&g_ep=EgoyMDI0MTAyOS4wIKXMDSoASAFQAw%3D%3D')

# Sleep for 5 seconds before clicking on the link at position (64,60)
input("press anykey  to continue")

# Move to position (64,60) and click() at that position (Note: you will not see your mouse move)
action = ActionBuilder(driver)
action.pointer_action.move_to_location(98, 170)
action.pointer_action.click()
action.perform()

time.sleep(3)
print('press arrow key down')
actions = ActionChains(driver)


i=0
links= 0
ulrsFile = open("urls.txt","w")
while(True):
    i=i+1
    actions.send_keys(Keys.ARROW_DOWN).perform()
    time.sleep(0.1)
    if i% 31 == 0:
        soup = BeautifulSoup(driver.page_source, 'html.parser')
        hrefs = [a['href'] for a in soup.find_all('a', href=True)]
        print(len(hrefs))
        if len(hrefs) == links:
            for link in hrefs:
                if "google.com/maps/place/" in link:
                    print(link)
                    ulrsFile.write(link+"\n")
            break
        links = len(hrefs)
            

