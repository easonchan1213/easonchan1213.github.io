---
layout: page
title: "Notes on Kaggle competition"
description: "sharing of knowledge on some useful tricks I found in Kaggle forum threads"
---
{% include JB/setup %}
> ####sharing of knowledge on some useful tricks I found in Kaggle forum threads


 
#[Criteo CTR prediction](https://www.kaggle.com/c/criteo-display-ad-challenge)

#####reference : I encourage you to read them through cause you might come across something that's new to you but not to me

1. https://www.kaggle.com/c/criteo-display-ad-challenge/forums/t/10555/3-idiots-solution-libffm


###Feature engineering:
1. Transforming infrequent features into a special tag. Conceptually, infrequent
features should only include very little or even no information, so it
should be very hard for a model to extract those information. In fact, these
features can be very noisy. We got significant improvement (more than 0.0005)
by transforming these features into a special tag.

2. Transforming numerical features (I1-I13) to categorical features.
Empirically we observe using categorical features is always better than
using numerical features. However, too many features are generated if
numerical features are directly transformed into categorical features, so we
use

v <- floor(log(v)^2)

to reduce the number of features generated.

3. Data normalization. According to our empirical experience, instance-wise
data normalization makes the optimization problem easier to be solved.
For example, for the following vector x

(0, 0, 1, 1, 0, 1, 0, 1, 0),

the standard data normalization divides each element of x by by the 2-norm
of x. The normalized x becomes

(0, 0, 0.5, 0.5, 0, 0.5, 0, 0.5, 0).

The hashing trick do not contribute any improvement on the leaderboard. We
apply the hashing trick only because it makes our life easier to generate
features. :)






<ul class="posts">
  {% for post in site.kaggles %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>