import random

template1 = ("It was about {num1} {time_measure} ago when I arrived at the hospital in a {transport}. "
             "The hospital was a {adj1} place, and there were a lot of {adj2} {noun1}s walking around. "
             "I met nurses who had {color} uniforms and {body_part}s that were as strong as steel. "
             "Before anyone could visit me, I told them they had to {verb1} first. "
             "I decorated my room with {num2} {noun2}s to make it feel more cozy. "
             "One of the doctors came in today, wearing a {noun3} around their {body_part2}. "
             "I found out that doctors eat {noun4}s for breakfast every day, and it's their secret to staying healthy! "
             "The funniest thing about being in the hospital was the giant {silly} {noun1} that kept popping up everywhere!")

template2 = ("This weekend, I'm going camping with my friend {person}. "
             "I packed my lantern, sleeping bag, and some {noun1}s for the trip. "
             "I'm so {feeling1} to sleep under the stars and {verb1} by the campfire. "
             "I'm a little {feeling2} though, because I heard we might run into a(n) {animal}, and they're pretty dangerous. "
             "During the day, we'll be hiking, fishing, and {verb2} by the lake. "
             "The {color} lake is known for its {verb_ing} spots, so we’ll definitely try that. "
             "Then, we’ll {adverb} hike through the forest for {num1} {time_measure}. "
             "If I see a {color2} {animal2} while hiking, I’ll definitely bring it home as my new pet! "
             "At night, we’ll tell {num2} crazy stories and roast {noun2}s around the campfire.")

template3 = ("Dear {person}, I'm writing to you from a beautiful, {adj1} castle in an enchanted forest. "
             "I arrived here after riding a {color} {animal} through the magical land of {place}. "
             "In this forest, there are {adj2} {creature1}s and {adj3} {creature2}s wandering around! "
             "Inside the castle, there is a {room} filled with a magical pool of {noun1}. "
             "I sleep every night on a {noun2} made of {noun3_plural}, and I dream of {adj4} {noun4_plural}. "
             "It feels like I’ve been here for {num1} {time_measure}, and I’m starting to think this might be my new home. "
             "I hope you can visit soon, but you’ll have to {verb_ing} on a {adj5} {noun5} to get here!")

templates = [template1, template2, template3]

print("Pick a template:")
print("1. Hospital story")
print("2. Camping story")
print("3. Magic castle story")
print("4. Random template")

choice = input("Enter 1, 2, 3 or 4: ")

if choice == "4":
    story_template = random.choice(templates)
else:
    story_template = templates[int(choice) - 1]

words = {}

#  Hospital Template
if story_template == template1:
    while True:
      try:
        words["num1"] = int(input("Type a number: "))
        break
      except ValueError:
        print("input valid type")
    words["time_measure"] = input("Type a measure of time: ")
    words["transport"] = input("Type a mode of transportation: ")
    words["adj1"] = input("Type an adjective: ")
    words["adj2"] = input("Type another adjective: ")
    words["noun1"] = input("Type a noun (person, place, thing): ")
    words["color"] = input("Type a color: ")
    words["body_part"] = input("Type a part of the body: ")
    words["verb1"] = input("Type a verb (action): ")
    while True:
      try:
        words["num2"] = int(input("Type another number: "))
        break
      except ValueError:
        print("input valid type")
    words["noun2"] = input("Type another noun: ")
    words["noun3"] = input("Type another noun: ")
    words["body_part2"] = input("Type another part of the body: ")
    words["verb2"] = input("Type another verb: ")
    words["noun4"] = input("Type another noun: ")
    words["silly"] = input("Type a silly word: ")

#Camping Template

elif story_template == template2:
    words["person"] = input("Type a person's name: ")
    words["noun1"] = input("Type a noun: ")
    words["feeling1"] = input("Type an adjective (feeling): ")
    words["verb1"] = input("Type a verb: ")
    words["feeling2"] = input("Type another adjective (feeling): ")
    words["animal"] = input("Type an animal: ")
    words["verb2"] = input("Type another verb: ")
    words["color"] = input("Type a color: ")
    while True:
       try:
         word=(input("Type a verb ending in -ing: "))
         if word.endswith("ing"):
            break
         else:
           print("input valid word")
       except TypeError:
        print("input valid word")

    words["adverb"] = input("Type an adverb: ")
    while True:
      try:
        words["num1"] = int(input("Type a number: "))
        break
      except ValueError:
        print("input valid type")   
    words["time_measure"] = input("Type a measure of time: ")
    words["color2"] = input("Type a color: ")
    words["animal2"] = input("Type another animal: ")
    while True:
      try:
        words["num2"] = int(input("Type another number: "))
        break
      except ValueError:
        print("input valid type")  
    words["silly"] = input("Type a silly word: ")
    words["noun2"] = input("Type another noun: ")

# Magic Castle Template
elif story_template == template3:
    words["person"] = input("Type a person's name: ")
    words["adj1"] = input("Type an adjective: ")
    words["color"] = input("Type a color: ")
    words["animal"] = input("Type an animal: ")
    words["place"] = input("Type a place: ")
    words["adj2"] = input("Type another adjective: ")
    words["creature1"] = input("Type a magical creature: ")
    words["adj3"] = input("Type another adjective: ")
    words["creature2"] = input("Type another magical creature: ")
    words["room"] = input("Type a room in a house: ")
    words["noun1"] = input("Type a noun: ")
    words["noun2"] = input("Type another noun: ")
    words["noun3_plural"] = input("Type a plural noun: ")
    words["adj4"] = input("Type an adjective: ")
    words["noun4_plural"] = input("Type a plural noun: ")
    while True:
      try:
        words["num1"] = int(input("Type a number: "))
        break
      except ValueError:
        print("input valid type")  
    words["time_measure"] = input("Type a measure of time: ")
    words["verb_ing"] = input("Type a verb ending in -ing: ")
    words["adj5"] = input("Type an adjective: ")
    words["noun5"] = input("Type a noun: ")

story = story_template.format(**words)

print("\nHere is your story:")
print(story)
