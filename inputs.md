# Samples from Gaokao Benchmark

## listening
The sample question is shown below, where there are four fields in total: `context`, `question`, `options`, and `answer`. Please note that for `context`, we provide the official transcript.
```json
{
    "context": "W: \"James, you've been watching TV for the whole evening. What's on?\" M: \"It's a science program on the origin of the universe. I'll give a presentation on it in my class tomorrow.\"", 
    "question": "what will James do tomorrow?", 
    "options": ["Watch a TV program.", "Give a talk.", "Write a report."], 
    "answer": "Give a talk."
}
```


## cloze-multiple-choice
The sample question is shown below, where there are four fields in total: `context`, `question_mark`, `options`, and `answer`.
```json
{
    "context": "During my second year at the city college, I was told that the education department was offering a \"free\" course, called Thinking Chess, for three credits. I <Q41> the idea of taking the class because, after all, who doesn't want to <Q42> a few dollars? More than that, I'd always wanted to learn chess. And, even if I weren't <Q43> enough about free credits, news about our <Q44> was appealing enough to me. He was an international grandmaster, which <Q45> I would be learning from one of the game's <Q46>. I could hardly wait to <Q47> him.\n\nMaurice Ashley was kind and smart, a former graduate returning to teach, and this <Q48> was no game for him; he meant business. In his introduction, he made it <Q49> that our credits would be hard-earned. In order to <Q50> the class, among other criteria, we had to write a paper on how we plan to <Q51> what we would learn in class to our future professions and ,<Q52>, to our lives. I managed to get an A in that <Q53> and learned life lessons that have served me well beyond the <Q54>.\n\nTen years after my chess class with Ashley, I'm still putting to use what he <Q55> me, \"The absolute most important <Q56> that you learn when you play chess is how to make good <Q57>. On every single move you have to <Q58> a situation, process what your opponent is doing and <Q59> the best move from among all your options.\" These words still ring true today in my <Q60> as a journalist.", 
    "question_mark": "<Q41>", 
    "options": ["put forward", "jumped at", "tried out", "turned down"], 
    "answer": "jumped at"
}
```


## cloze-hint
The sample question is shown below, where there are four fields in total: `context`, `question_mark`, `hint`, and `answer`. Note that `hint` can be `null` as well. There could be multiple correct answers where we use `/` to separate each.
```json
{
    "context": "According to a review of evidence in a medical journal, runners live three years <Q61> than non-runners. You don't have to run fast or for long <Q62> the benefit. You may drink, smoke, be overweight and still reduce your risk of <Q63> early by running.\n\nWhile running regularly can't make you live forever, the review says it <Q64> more effective at lengthening life <Q65> walking, cycling or swimming. Two of the authors of the review also made a study published in 2014 <Q66> showed a mere five to 10 minutes a day of running reduced the risk of heart disease and early deaths from all <Q67>.\nThe best exercise is one that you enjoy and will do. But otherwise it's probably running. To avoid knee pain, you can run on soft surfaces, do exercises to <Q68> your leg muscles, avoid hills and get good running shoes. Running is cheap, easy and it's always <Q69>. If you are time poor, you need run for only half the time to get the same benefits as other sports, so perhaps we should all give <Q70> a try.", 
    "question_mark": "<Q70>", 
    "hint": null,  
    "answer": "it/running"
}
```


## reading-multiple-choice
The sample question is shown below, where there are four fields in total: `context`, `question`, `options`, and `answer`.
```json
{
    "context": "Washington, D.C. Bicycle Tours\n\nCherry Blossom Bike Tour in Washington, D.C.\n\nDuration: 3 hours\n\nThis small group bike tour is a fantastic way to see the world-famous cherry trees with beautiful flowers of Washington, D.C. Your guide will provide a history lesson about the trees and the famous monuments where they blossom. Reserve your spot before availability and the cherry blossoms disappear!\n\nWashington Capital Monuments Bicycle Tour\n\nDuration: 3 hours (4 miles)\n\nJoin a guided bike tour and view some of the most popular monuments in Washington, D. C. Explore the monuments and memorials on the National Mall as your guide shares unique facts and factory at each stop.\n\nCapital City Bike Tour in Washington, D. C.\n\nDuration: 3 hours\n\nMorning or Afternoon, this bike tour is the perfect tour for D.C. newcomers and locals looking to experience Washington, D. C. in a healthy way with minimum effort. Knowledgeable guides will entertain you with the most interesting stories about Presidents, Congress, memorials, and parks. Comfortable bikes and a smooth tour route make cycling between the sites fun and relaxing.\n\nWashington Capital Sites at Night Bicycle Tour\n\nDuration: 3 hours (7 miles)\n\nJoin a small group bike tour for an evening of exploration in the heart of Washington, D. C. Get up close to the monuments and memorials as you bike the sites of Capitol Hill and the National Mall. Frequent stops are made for photo taking as your guide offers unique facts and history. Tour includes bike, helmet, and bottled water. All rides are equipped with reflective vests and safety lights.", 
    "question": "Which tour do you need to book in advance?", 
    "options": ["Cherry Blossom Bike Tour in Washington, D. C.", "Washington Capital Monuments Bicycle Tour.", "Capital City Bike Tour in Washington, D. C.", "Washington Capital Sites at Night Bicycle Tour."], 
    "answer": "Cherry Blossom Bike Tour in Washington, D. C."
}
```

## reading-cloze
The sample question is shown below, where there are four fields in total: `context`, `question_mark`, `options`, and `answer`.
```json
{
    "context": "Color is fundamental in home design-something you'll always have in every room. A grasp of how to manage color in your spaces is one of the first steps to creating rooms you'll love to live in. Do you want a room that's full of life? Professional? Or are you just looking for a place to relax after a long day? <Q36>, color is the key to making a room feel the way you want it to feel.\n\nOver the years, there have been a number of different techniques to help designers approach this important point. <Q37>, they can get a little complex. But good news is that there're really only three kinds of decisions you need to make about color in your home: the small ones, the medium ones, and the large ones.\n\n<Q38>. They're the little spots of color like throw pillows, mirrors and baskets that most of us use to add visual interest to our rooms. Less tiring than painting your walls and less expensive than buying a colorful sofa, small color choices bring with them the significant benefit of being easily changeable.\n\nMedium color choices are generally furniture pieces such as sofas, dinner tables or bookshelves. <Q39>. They require a bigger commitment than smaller ones, and they have a more powerful effect on the feeling of a space.\n\nThe large color decisions in your rooms concern the walls, ceilings, and floors. Whether you're looking at wallpaper or paint, the time, effort and relative expense put into it are significant. <Q40>.", 
    "question_mark": "<Q36>", 
    "options": ["While all of them are useful", "Whatever you're looking for", "If you're experimenting with a color", "Small color choices are the ones we're most familiar with", "It's not really a good idea to use too many small color pieces", "So it pays to be sure, because you want to get it right the first time", "Color choices in this range are a step up from the small ones in two major ways"], 
    "answer": "Whatever you're looking for"
}
```


## writing-grammar
The sample question is shown below, where there are two fields in total: `original` and `edits`. Note that for each error, there could be multiple ways of correcting it, where we use a list to represent the possible corrections.
```json
{
    "original": "During my last winter holiday, I went to countryside with my father to visit my grandparents. I find a big change there. The first time I went there, they were living in a small house with dogs, ducks, and another animals. Last winter when I went here again, they had a big separate house to raise dozens of chicken. They also had a small pond which they raised fish. My grandpa said last summer they earned quite a lot by sell the fish. I felt happily that their life had improved. At the end of our trip, I told my father that I planned to return for every two years, but he agreed.", 
    "edits": [
        {"start_idx": 8, "end_idx": 8, "corrections": ["the"]},
        {"start_idx": 17, "end_idx": 18, "corrections": ["found"]}, 
        {"start_idx": 39, "end_idx": 40, "corrections": ["other"]}, 
        {"start_idx": 46, "end_idx": 47, "corrections": ["there"]}, 
        {"start_idx": 58, "end_idx": 59, "corrections": ["chickens."]}, 
        {"start_idx": 65, "end_idx": 65, "corrections": ["in"]}, 
        {"start_idx": 65, "end_idx": 66, "corrections": ["which", "where"]}, 
        {"start_idx": 80, "end_idx": 81, "corrections": ["selling"]},
        {"start_idx": 85, "end_idx": 86, "corrections": ["happy"]}, 
        {"start_idx": 110, "end_idx": 111, "corrections": ["and"]}
    ]
}
```

## writing-essay
The sample question is shown below, where there are two fields in total: `question` and `example_essay`. Note that we use Google translate to translate the original Chinese question into its English version.
```json
{
    "question": "Assuming you are Li Hua, your New Zealand friend Terry will be visiting a Chinese friend's house and emailing you about customs. Please reply to the email, including: 1. Arrival time; 2. Appropriate gifts; 3. Table manners. Here are some requirements: 1. The number of words is about 100; 2. Details can be added appropriately to make the writing coherent.", 
    "example_essay": "Dear Terry, How are you doing? In your last letter, you asked me about being a guest to a Chinese friend's home. Now, I am writing to inform you of some relevant details. To begin with, according to our tradition, you are supposed to arrive early, so that you can help the family prepare the dinner, which is meaningful and interesting. Besides, you'd better bring some gifts, like a book or a Chinese knot. What's more, when you are enjoying the meal, you need to avoid making noises while chewing food. Hopefully, these suggestions would be helpful for you. I have the confidence that you will have a great time. Best wishes! Yours, Li Hua"
}
```
