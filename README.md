# Prompt Flow Demo - Trivia Assistant

This repository contains ancillary data/notebook routines to support a demo of Prompt Flow designed to build a trivia-assistant bot. 

Briefly, within this repo the file `formatted_trivia_questions.csv` contains sample trivia questions of the format:

```
json
{
    "Question": "Which team beat American Samoa 31-0 in a qualifying match for the 2002 World Cup, but still failed to qualify?", 
    "Answer": "Australia", 
    "AnswerType": "WikipediaEntity", 
    "QuestionId": "qz_1670", 
    "Entity": "australia", 
    "BackgroundContent": "Australia's National Soccer Team, also known as the Socceroos, made headlines during the qualifying matches for the 2002 World Cup. One particular match that garnered attention was their encounter with American Samoa, a small island nation in the South Pacific. The Socceroos defeated American Samoa with an astonishing scoreline of 31-0. However, despite this resounding victory, Australia ultimately failed to qualify for the prestigious tournament.\n\nThe match between Australia and American Samoa took place on April 11, 2001, at the International Sports Stadium in Coffs Harbour, Australia. The Socceroos, led by their coach Frank Farina, were determined to secure a convincing win to boost their chances of qualifying for the 2002 World Cup. On the other hand, American Samoa, under the guidance of their coach Tunoa Lui, were eager to put up a strong fight against their more experienced opponents.\n\nFrom the very beginning, it was clear that Australia had the upper hand. The Socceroos dominated possession and constantly attacked American Samoa's defense. Tim Cahill, Mark Viduka, and Harry Kewell were among the standout players for Australia, showcasing their skill and scoring prowess throughout the match. American Samoa, on the other hand, struggled to keep up with the pace and intensity of their opponents.\n\nThe goals started pouring in for Australia early on in the match. Tim Cahill opened the scoring in the 4th minute, setting the tone for what would be a goal fest. Mark Viduka, Australia's star striker, also made a significant impact, scoring multiple goals and showcasing his clinical finishing ability. Harry Kewell, known for his speed and agility, proved to be a constant threat to American Samoa's defense, contributing several goals to the scoreline.\n\nAs the match progressed, it became evident that Australia's dominance was overwhelming. American Samoa's defense was unable to contain the relentless attacks from the Socceroos, and their goalkeeper, Nicky Salapu, faced a barrage of shots throughout the game. Despite his best efforts, Salapu was unable to prevent Australia from finding the back of the net time and time again.\n\nThe match ended with a final score of 31-0 in favor of Australia, a result that would go down in history as one of the most lopsided victories in international soccer. The Socceroos had achieved their objective of securing a convincing win, but their journey to the 2002 World Cup was far from over.\n\nDespite their dominant performance against American Samoa, Australia's failure to qualify for the 2002 World Cup came as a shock to many. The Socceroos faced stiff competition in their qualifying group, which included teams like Iran and Saudi Arabia. Despite their best efforts, Australia finished third in their group, missing out on a spot in the tournament.\n\nThe match against American Samoa remains a memorable moment in Australian soccer history. It showcased the Socceroos' attacking prowess and highlighted the vast difference in skill and experience between the two teams. While Australia's victory was impressive, it ultimately served as a bittersweet reminder of their failure to qualify for the 2002 World Cup."
}
```

The questions in this dataset were captured from the open-source [TriviaQA Dataset](https://nlp.cs.washington.edu/triviaqa/index.html)
```[Mandar Joshi, Eunsol Choi, Daniel Weld, Luke Zettlemoyer. TriviaQA: A Large Scale Distantly Supervised Challenge Dataset for Reading Comprehension
In Association for Computational Linguistics (ACL) 2017, Vancouver, Canada.](https://arxiv.org/abs/1705.03551)```

Here, we have selected a sample of ~9,500 trivia question/answer pairs, and generated background articles (using `gpt-35-turbo`) to support answering via a retrieval augmented generation process. Moreover, we have generated embeddings for all 'Background Content' using the `text-embedding-ada-002` model from Azure OpenAI to enable creation of a vector index.

The notebook at `ai_search_index_operations.ipynb` contains sample code to create a populate an Azure AI Search index.
