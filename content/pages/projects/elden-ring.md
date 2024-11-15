---
type: ProjectLayout
title: ELDEN RING
date: '2023-06-13'
client: ''
description: >-
  Hello, this project is for Fromsoftware fans, people interested in playing
  Elden Ring and open world games, especially those who want to build a
  character with physical strength or dexterity as their main ability, also
  search through the data and see the relationships or insights we can find.
featuredImage:
  type: ImageBlock
  url: /images/Elden Ring.png
  altText: ELDEN RING
  caption: ELDEN RING
media:
  type: ImageBlock
  url: /images/Elden Ring.png
  altText: ELDEN RING
  caption: ELDEN RING
bottomSections: []
metaTags: []
colors: colors-a
---
## USED LIBRARIES/PACKAGES IN THIS PROJECT

*   **jovian** (to upload, save and share the contents of my notebook)

*   **numpy** (as np is one of the very famous packages for working with arrays in python)

*   **pandas** (Is greatly used in analysis of data and making dataframe)

*   **matplotlib** (Lets make our Analyzation fun and interative with the visualization library matplotlib)

*   **seaborn** (Adding more colours into matplotlib visualization)

## DATA PREPARATION AND CLEANING

### Import libraries

import pandas as pd

import matplotlib as mpl

import matplotlib.pyplot as plt

import seaborn as sns

import numpy as np

%matplotlib inline

### Downloading the Dataset

df = pd.read\_csv('elden\_ring\_weapon.csv')

### Handling Null Values

df.isnull().values.any()

sns.heatmap(df.isnull(), cbar=False) plt.title('Null Values Heatmap') plt.show()

![](https://sebaslon.com/images/output_20_0.png)

df.isnull().sum().sort\_values(ascending = False)

Above in the heatmap and table, we can see that there are none null values in the dataset. . therre is no need to handle null data points, but there are some (-), so we need to change them for a value 0, then we can dive into EDA and modeling.

df\['Phy.1']=df\['Phy.1'].replace('-', '0').astype('int')

df\['Phy']=df\['Phy'].replace('-', '0').astype('int')

df\['Str']=df\['Str'].replace('N', None ).astype('object')

df\['Dex']=df\['Dex'].replace('-', None ).astype('object')

df\['Rst']=df\['Rst'].replace('NULL', 0 ).astype('int')

df\['Rst'] = df\['Rst'].fillna(0)

## EXPLORATORY ANALYSIS AND VISUALIZATION

### Inspect for data

df.head(5)

df.columns

df.shape

df.info()

df.describe()

pd.set\_option('display.max\_rows', None)

pd.set\_option('display.max\_columns', None)

df

### styling

sns.set\_style('darkgrid') mpl.rcParams\['font.size'] = 15 mpl.rcParams\['figure.figsize'] = (8, 4) mpl.rcParams\['figure.facecolor'] = '#00000000'

## ASKING AND ANSWERING QUESTIONS

### Q1: what is the range of weight of the weapon that is repeated more & which is the heaviest weapon & How much the top 5 weapons weigh ?

sns.histplot(data=df, x='Wgt') plt.ylabel("Count") plt.xlabel("Weight") plt.title('Weight of the weapons')

![](https://sebaslon.com/images/output_43_1.png)

Most of the weapons weights are in the range is between 5 > 0

df\[df\['Wgt'] == df\['Wgt'].max()]

The heaviest weapon is the Giant-Crusher

![](https://assets.gamepur.com/wp-content/uploads/2022/04/22193303/elden_ring_giant_crusher-1.jpg)

df\_wgt= df.Wgt.sort\_values(ascending=False).head(5)

df\_wgt.values

The heaviest 5 weapons weigh : 26.5, 23.5, 23. , 23. , 22.

![](https://static0.gamerantimages.com/wordpress/wp-content/uploads/2022/03/elden-ring-best-colossal-weapons.jpg)

There are just a few weapons that weights a sustancial amount compared among the set of weapong, if you want build your character with pyshical streght, you should aim to obtain one of these

### Q2: what is the most repeated physical damage among the upgraded weapons & which weapon make the most damage ?

sns.histplot(data=df, x='Phy') plt.title('physical damage')

![](https://sebaslon.com/images/output_54_1.png)

The most repeated damage among the improved weapons is around 300

df\[df\['Phy'] == df\['Phy'].max()]

The improved weapon that makes more damage is the Jar Cannon

![](https://xboxplay.games/uploadStream/25747.jpg)

### Q3: What is the group of weapons that have more weapons en compare the other groups & how many katanas there are and which is best?

df\['Type'].unique()

top\_types= df.Type.value\_counts()

top\_types

plt.figure(figsize=(16,9)) plt.title("Weapons") plt.pie(top\_types, labels=top\_types.index, autopct='%1.f%%', startangle=200);

![](https://sebaslon.com/images/output_63_0.png)

The group of weapons with the most of them are the straight swords, followed by the gratswords, the glintstone staffs, halberds, and spears.

![](https://preview.redd.it/wzpfo60317x81.png?width=1846\&format=png\&auto=webp\&s=150bfce86a263ab2f1cf04a5699e041cdbe650f6)

top\_types\['Katana']

There are eight types of katana

![](https://fictionhorizon.com/wp-content/uploads/2022/06/Elden-Ring-Katana.jpg)

katanas=df\[df\['Type'] == 'Katana'] katanas

Best\_katana=katanas\[katanas\['Upgrade'] == 'Smithing Stones'] Best\_katana

For the ones who love Katanas you should get the Nagakiba, thus is easier to upgrade with the Smithing Stones, which are more abundant, or the Uchigatana being the starting weapon of the Samurai class, and could get from the beginning a decent amount of physical damage

### Q4: With which type of stone is more often improved the weapons Smithing Stones vs Somber Smithing Stones ?

df\['Upgrade'].unique()

top\_stones = df.Upgrade.value\_counts()

top\_stones

plt.figure(figsize=(8,4)) plt.title("Smithing stones vs. Somber Smithing stones") plt.pie(top\_stones, labels=top\_stones.index, autopct='%1.2f%%', startangle=75);

![](https://sebaslon.com/images/output_76_0.png)

With the stone Blacksmith Stones, weapons are improved more often, therefore blacksmith stones are more abundant, and if some arams have good improvement with this stone, they are good options.

![](https://oyster.ignimgs.com/mediawiki/apis.ign.com/elden-ring/7/76/Somber1.jpg)

### Q5: What percentages of scalability do you have with strength ability between the categories?

df\['Str'].unique()

top\_str = df.Str.value\_counts()

top\_str

top\_str = df.Str.value\_counts(normalize=True).reset\_index().rename(columns={'Str':'Count','index':'Str'}) top\_str

top\_Categories\_str =top\_str.head(6).sort\_values(by = \['Str'],ascending = True)

sns.barplot(x = top\_Categories\_str.Str ,y= top\_Categories\_str.Count) plt.title(' % Scalability with strength per category')

![](https://sebaslon.com/images/output_86_1.png)

The majority of weapons that scale with strength are category D followed by C, B, E, and the best would be A, and S, the latter being the rarest and best.

### Q6: What percentages of scalability do you have with dextrous ability between the categories?

df\['Dex'].unique()

top\_Dex = df.Dex.value\_counts(normalize=True).reset\_index().rename(columns={'Dex':'Count','index':'Dex'}) top\_Dex

top\_Categories\_Dex =top\_Dex.head(4).sort\_values(by = \['Dex'],ascending = True)

sns.barplot(x = top\_Categories\_Dex.Dex ,y= top\_Categories\_Dex.Count) plt.title(' % Scalability with Dextrous per category')

![](https://sebaslon.com/images/output_92_1.png)

Most of the weapons that scale right-handed are category D followed by C, B, E, and according to this data set there would be no weapons with scalability in A or S

### Q7: what percentage of weapons have the most common critical damage?

df\['Cri'].unique()

top\_cri = df.Cri.value\_counts()

top\_cri= df.Cri.value\_counts(normalize=True).reset\_index().rename(columns={'Cri':'Count','index':'Cri'}) top\_cri

plt.figure(figsize=(10,5)) plt.xticks(rotation=0) plt.title("% Critical damage among set of weapons") sns.barplot(y=top\_cri.Count, x=top\_cri.Cri);

![](https://sebaslon.com/images/output_98_0.png)

The most common critical damage among weapons is 91.25% with 100, 7.16% with 110, and only about 1.6% of weapons have a critical damage of between 110<x<140 and those being the rarest and best.

### Q8:What kind of relationship is between weight and resistance?

ax = sns.scatterplot(x="Rst", y="Wgt", data=df, hue='Str') ax.set\_title("Weight vs. Resistence") ax.set\_xlabel("Resistence") ax.set\_ylabel("Weight");

![](https://sebaslon.com/images/output_101_0.png)

If you remove some atypical data you can see a correlation between the weight and resistance of weapons positive, which is a very interesting correlation when wanting to also have a lot of resistance.

## INFERENCES AND CONCLUSION

Starting elden ring focused on maximizing character builds with strength ability is a very good decision, as they have better weapons to be scaled, in addition to having a good range of physical damage, and thanks to the wide variety of weapons you can choose between 30 types of weapons, and if you want to have greater resistance you should choose one of the colossal weapons or if you do not seek high resistance katanas are for you, if you like katanas it would be good to get the nagakiba, so it's easier to improve with the smithing stone, which are more abundant for the physical damage it has, or the uchigatana being the initial weapon of the samurai class, and you could get from it Initially a decent amount of physical damage.

## FUTURE WORKS

*   Try other ways to build a character.

*   Try other data sets besides weapons

*   Do web scraping and collect the raw data from other parts of the game, and do EDA





