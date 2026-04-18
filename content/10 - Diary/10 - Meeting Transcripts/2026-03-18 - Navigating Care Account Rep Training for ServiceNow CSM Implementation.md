# Transcript
WEBVTT

1
00:00:00.000 --> 00:00:01.170
aaronbanister: Hello, everybody.

2
00:00:01.710 --> 00:00:11.370
aaronbanister: Just a quick rundown on the agenda. This should go pretty quickly. I don't want to throw too much at you, because ServiceNow…

3
00:00:11.400 --> 00:00:29.330
aaronbanister: It has a lot to offer, so sometimes it can be a bit overwhelming… overwhelming when you first see it. So I'm gonna try to do my best to boil it down to only the parts that y'all need to interact with, and hopefully that'll keep things simple. So I'm gonna show you how to navigate the system.

4
00:00:29.870 --> 00:00:33.710
aaronbanister: I'm going to demonstrate the creation and modification of an account.

5
00:00:34.190 --> 00:00:40.160
aaronbanister: We'll show account team members and how those are, attached to accounts.

6
00:00:40.540 --> 00:00:49.460
aaronbanister: I'm gonna introduce the concept of install-based items and sold products, and these map to instances and modules, respectively.

7
00:00:49.750 --> 00:00:55.720
aaronbanister: I'm gonna show where contracts go, and then I'll close it out with some user interface tips.

8
00:00:56.160 --> 00:00:59.220
aaronbanister: Any questions on the agenda before we begin?

9
00:01:02.440 --> 00:01:11.010
aaronbanister: Alright, I will take silence as golden, and this is what it looks like when you first log into ServiceNow.

10
00:01:11.380 --> 00:01:21.180
aaronbanister: ServiceNow's backend, specifically. When you first click on the ServiceNow test icon in your OneID dashboard, it might look more like this.

11
00:01:26.660 --> 00:01:31.939
aaronbanister: And… that's okay. This is our employee center, and it's the default landing page for ServiceNow.

12
00:01:33.230 --> 00:01:46.980
aaronbanister: I've sent a link to Tom and Sachaya that they can share with you, that'll make it really easy to get to the backend if you are missing this button right here. But if you do see the ITIL home button, that's your quick access link into the backend of the platform.

13
00:01:47.900 --> 00:01:49.480
aaronbanister: And once you're in here.

14
00:01:49.840 --> 00:01:58.569
aaronbanister: You've got this navigation bar at the top, and by default, you'll probably only have it at the top, like you see here.

15
00:01:58.910 --> 00:02:04.809
aaronbanister: To get somewhere in the system, you use the all search here, and you type in where you want to go.

16
00:02:05.060 --> 00:02:08.840
aaronbanister: So if we're gonna go to the accounts module, I'll just type in Accounts.

17
00:02:09.340 --> 00:02:10.410
aaronbanister: And…

18
00:02:10.530 --> 00:02:15.550
aaronbanister: As you can see, there's a few options, but the one that we want is here under Customer Service Accounts.

19
00:02:20.420 --> 00:02:32.519
aaronbanister: Okay, and this is what a list view looks like in ServiceNow. Pretty much anywhere you go in ServiceNow, where data is stored, you'll see the data by default displayed in this way, in a list format.

20
00:02:33.160 --> 00:02:38.549
aaronbanister: And then when you click on a record from the list, you'll be taken into the form view of that record.

21
00:02:39.330 --> 00:02:44.640
aaronbanister: And this is where you're gonna start to see a lot more of the familiar metadata inside of a record.

22
00:02:46.870 --> 00:02:52.600
aaronbanister: So, before we get into an existing account, I'll quickly show how to create a new one.

23
00:02:52.930 --> 00:02:55.579
aaronbanister: That's done from the list view.

24
00:02:56.340 --> 00:02:58.030
aaronbanister: And you'll just click this new button.

25
00:02:58.990 --> 00:03:10.430
aaronbanister: And you'll just start filling out the form fields. If there's any required form fields, those will be labeled with an asterisk, but on the account table, none of these fields are required, so you can…

26
00:03:10.590 --> 00:03:14.299
aaronbanister: Really just enter, as much or as little as you want to enter.

27
00:03:14.440 --> 00:03:16.250
aaronbanister: Let's call this a test account.

28
00:03:19.060 --> 00:03:31.709
aaronbanister: Once you have the form filled out how you want it, you can submit it to the database two ways. There's this submit button here, which will save the record as you've configured it, and it will take you back to the previous screen.

29
00:03:32.210 --> 00:03:47.949
aaronbanister: If you don't want to go back to the previous screen, say you wanted to stay here and add more information, you can right-click this header bar, and you'll get some more options, in this case, such as Save. Save is gonna insert the record on the table, and it will

30
00:03:48.280 --> 00:03:56.950
aaronbanister: pretty much… it'll sort of initialize the record, so you can see things you couldn't see before, such as these related lists at the bottom, which we'll get into. But this is…

31
00:03:57.150 --> 00:03:59.170
aaronbanister: Just more places to store data.

32
00:04:01.320 --> 00:04:02.459
aaronbanister: And as far as…

33
00:04:02.460 --> 00:04:03.320
Tom McGovern: for you.

34
00:04:03.320 --> 00:04:03.870
aaronbanister: Go ahead.

35
00:04:03.870 --> 00:04:15.850
Tom McGovern: So, typically, a lot of our business, as Susan and implementation… another team knows, is that they're managed service organizations from the One Oncology team. We don't have that much business that's not related to one oncology.

36
00:04:16.029 --> 00:04:18.290
Tom McGovern: Would it be safe to say that…

37
00:04:18.410 --> 00:04:31.259
Tom McGovern: well, Susan's team is the one who starts it out of the implementation, the CSMs. Would that account already be existing for the most part, because Navigating Care is coming in after they've signed a managed service organization contract?

38
00:04:31.260 --> 00:04:38.819
Tom McGovern: And as such, they've already been added into ServiceNow. Should we have that thought process to avoid trying to create a duplicate account?

39
00:04:39.260 --> 00:04:39.930
aaronbanister: Yeah.

40
00:04:39.930 --> 00:04:41.990
Tom McGovern: That type of world I'm trying to think through.

41
00:04:41.990 --> 00:04:51.730
aaronbanister: It's a good question, and I think it has a lot to do with, how our legal team is gonna integrate with this business process. Okay. Justice has mentioned that to me.

42
00:04:51.730 --> 00:05:04.299
aaronbanister: Sort of vaguely so far, but the way I'm understanding the vision is our… those contracts will get signed on the legal side, and there will be automations that fire from their side of ServiceNow to create accounts.

43
00:05:04.480 --> 00:05:07.960
aaronbanister: In most cases, you shouldn't have to create an account manually.

44
00:05:08.630 --> 00:05:10.609
aaronbanister: If that answers your question.

45
00:05:10.850 --> 00:05:11.770
Tom McGovern: Yeah, thank you.

46
00:05:12.150 --> 00:05:16.020
aaronbanister: But it's still good to show what it looks like to create a new record of any kind, because you might.

47
00:05:16.020 --> 00:05:16.500
Tom McGovern: Absolutely.

48
00:05:16.500 --> 00:05:29.760
aaronbanister: create new records on other tables that are related to accounts, this, that, or the other. The experience is the same, really, on every table in ServiceNow. There's a new button, and then there's a form that appears where you can enter data.

49
00:05:30.260 --> 00:05:34.930
Justice West: Aaron, one thing we didn't talk about, this would be on me,

50
00:05:35.230 --> 00:05:43.840
Justice West: is to show them, and if you want to try to take a stab at it now, feel free. If not, we can come back with this, which I'd imagine most accounts…

51
00:05:44.390 --> 00:05:58.399
Justice West: of anybody we'd mess with, if it's new, would come… would already be a company, if that makes sense, not to distract the broader team from getting in the weeds here. So, like, they would be a company because, like, the legal team would be working with them further upstream, potentially.

52
00:05:58.780 --> 00:06:04.950
Justice West: So… would… can you show how, like, if they're an existing company, you would just…

53
00:06:05.060 --> 00:06:07.319
Justice West: Flip them into an account, if needed.

54
00:06:08.590 --> 00:06:11.109
aaronbanister: I don't know that we've covered that.

55
00:06:11.110 --> 00:06:11.929
Justice West: We can take that back.

56
00:06:11.930 --> 00:06:18.109
aaronbanister: functionality, yeah, because… I believe this table extends the core company table.

57
00:06:18.110 --> 00:06:18.880
Justice West: Yes.

58
00:06:18.880 --> 00:06:21.900
aaronbanister: But yeah, if… Let me…

59
00:06:21.900 --> 00:06:22.509
Salena Reeves: Just the story.

60
00:06:23.070 --> 00:06:24.700
Salena Reeves: work to find…

61
00:06:25.810 --> 00:06:31.000
Salena Reeves: like, some var… so does the search capability work to find some variation of it? Because I know that…

62
00:06:31.790 --> 00:06:36.380
Salena Reeves: In our other systems, like, if we are… looking up an account.

63
00:06:36.700 --> 00:06:40.430
Salena Reeves: Go look up variations of it first and make sure that we're not duplicating it.

64
00:06:41.170 --> 00:06:44.650
aaronbanister: Yeah, I'll demonstrate how to do a quick search, so…

65
00:06:44.800 --> 00:06:49.800
aaronbanister: If I go back to the accounts table…

66
00:06:50.030 --> 00:06:53.279
aaronbanister: Each of these columns are searchable, and you can also…

67
00:06:53.440 --> 00:07:02.130
aaronbanister: use this filter icon to make a very, like, specific search query, if that's what you want to do. But, if, say, this list was, like.

68
00:07:02.260 --> 00:07:10.150
aaronbanister: 3 pages long and you didn't want to look through it all visually, you could use this name column and throw in a search term like Texas.

69
00:07:11.110 --> 00:07:14.169
aaronbanister: And then you'd see… here's one called Texas Oncology.

70
00:07:16.130 --> 00:07:22.079
aaronbanister: Or if you didn't know, necessarily exactly what it started with. You could say…

71
00:07:22.240 --> 00:07:26.949
aaronbanister: I forget the name exactly, but I know that it contains the term specialists.

72
00:07:27.200 --> 00:07:34.700
aaronbanister: So you can use this wildcard search right here with the asterisk, and that'll give you any results that contain the word special.

73
00:07:35.030 --> 00:07:37.410
aaronbanister: So you've got 3 that say specialists.

74
00:07:38.230 --> 00:07:39.699
aaronbanister: Does that answer your question?

75
00:07:41.220 --> 00:07:41.880
Salena Reeves: Hmm.

76
00:07:42.160 --> 00:07:44.689
Salena Reeves: But that's only if it already exists as an account.

77
00:07:44.960 --> 00:07:50.820
Salena Reeves: It wouldn't give me a different variation of, like, Companies, or leads, or other…

78
00:07:51.810 --> 00:07:55.949
aaronbanister: Correct, yeah. The search here on this specific

79
00:07:55.970 --> 00:08:13.820
aaronbanister: list view is only going to show records on this table, but there are global places to search. Like I said, accounts extends companies, so you could do a similar query on the company table, and you'd see, maybe they're not a customer account, but they are a company in the database.

80
00:08:13.820 --> 00:08:27.160
aaronbanister: And then we can also open up this global search that searches the entire database, and we can… we can make sure that companies and accounts and whatever other objects you're interested in, are indexed behind this search bar as well.

81
00:08:27.530 --> 00:08:37.290
Justice West: Absolutely, that's on me for not having, thought about that scenario where, like, legal would probably potentially have this entered in the system further upstream.

82
00:08:37.679 --> 00:08:47.060
Justice West: But that'll be an easy thing I can… we can show… I'm very confident it's super easy, and I'll give you instructions and show you how to do that.

83
00:08:47.640 --> 00:08:48.739
Salena Reeves: Okay, perfect, thank you.

84
00:08:50.840 --> 00:08:52.830
Justice West: Sorry, Aaron. Oh, yeah, I'm good.

85
00:08:53.440 --> 00:09:00.729
aaronbanister: Yeah, a lot of those automations that we might talk about, that this demonstration could remind us of.

86
00:09:00.850 --> 00:09:17.799
aaronbanister: haven't been fully built yet, but that's kind of on purpose, because you need to have a good understanding of the data architecture first. So that's really what the scope of this demonstration is about, is just to show where things will live and, and how they interrelate.

87
00:09:20.940 --> 00:09:21.980
aaronbanister: Okay.

88
00:09:22.810 --> 00:09:39.619
aaronbanister: So, we showed how to create a new account. Modifying it is very simple. You just click into one and you can change all of these data points to whatever you need. Similar user experience when you're modifying an account is you've got this button up here to update now, instead of submit.

89
00:09:39.630 --> 00:09:53.359
aaronbanister: But it behaves similarly, in that it will insert your updates, and it will take you back a screen, to the last screen that you were on. If you don't want that, you can just add your update, right-click and hit save. That works the same way for modifying.

90
00:09:55.300 --> 00:09:58.170
aaronbanister: Moving on now to related…

91
00:09:58.800 --> 00:10:02.939
aaronbanister: Related objects, the first one being account team members.

92
00:10:03.410 --> 00:10:22.859
aaronbanister: I understand that this used to be captured on the actual account object in Salesforce. Here in ServiceNow, this information is exposed and surfaced on the account object, but it's technically stored on this account team members table, which is shown as a related list under the account.

93
00:10:23.840 --> 00:10:34.339
aaronbanister: This allows you to, sort of be flexible. You can add as many team members to an account as you want, and you can have as many different responsibilities as you want as well.

94
00:10:38.930 --> 00:10:54.979
aaronbanister: Install-based items. This is a further abstraction from the accounts object in Salesforce, where a lot of this information was stored on the account. Now we're bringing some of it out of the account and putting it into an install-based item, and this essentially represents an instance.

95
00:10:55.570 --> 00:10:58.530
aaronbanister: And I'll click into this instance to show you what that looks like.

96
00:11:03.810 --> 00:11:09.549
aaronbanister: This might have been a… Poor example being that there's probably more detailed

97
00:11:09.780 --> 00:11:12.509
aaronbanister: Instances in here. Let's try this one.

98
00:11:18.120 --> 00:11:23.359
aaronbanister: Okay, so we picked Texas Oncology's Gulf instance.

99
00:11:23.710 --> 00:11:27.980
Salena Reeves: That's not gonna be a good one, because it's a subcategory underneath the big Texas one.

100
00:11:27.980 --> 00:11:30.650
aaronbanister: Oh, okay. Let me go back to the account.

101
00:11:31.160 --> 00:11:34.170
aaronbanister: You can tell me what looks like a good example.

102
00:11:35.810 --> 00:11:37.650
Salena Reeves: Utah should have information in it, right guys?

103
00:11:38.380 --> 00:11:39.090
aaronbanister: Let's try again.

104
00:11:39.090 --> 00:11:41.690
Heather Chase: Well, it's all dummy information, but yeah.

105
00:11:42.380 --> 00:11:43.120
Salena Reeves: Okay.

106
00:11:43.880 --> 00:11:44.779
Suchaya Laddaphan: Should have enough.

107
00:11:46.100 --> 00:11:50.079
Tom McGovern: It's real. We took it out of the extract from Salesforce and had to populate it with it.

108
00:11:51.630 --> 00:12:02.190
aaronbanister: There's an example of what that looks like. There's a lot of fields on here, by the way, that you'll see that are blank. These are out-of-box fields that we can modify and hide, if…

109
00:12:02.300 --> 00:12:11.419
aaronbanister: if it's necessary. But we've left them here just in case they serve some, you know, at least get the gears turning on how they could serve some purpose. Yeah.

110
00:12:11.600 --> 00:12:14.760
Justice West: And Aaron, I can speak to that a little bit, so this was…

111
00:12:15.170 --> 00:12:34.439
Justice West: some of Aaron and I's decision-making, and we can talk through, but as Aaron mentioned, like, I like, generally, especially when people are first using the system, it's different changes, different fields, we'll expose more things, just so there's, like, awareness of what's there, so you kind of understand the structure and how everything's kind of set up.

112
00:12:34.570 --> 00:12:49.860
Justice West: Obviously, you're probably not going to use all of them day one, and actually… so, I didn't have… I didn't have time to prep with this with Erin, because I just met with Debbie less than an hour ago, but one of the things we do want to do over time is give you guys some, like, more

113
00:12:50.350 --> 00:12:54.209
Justice West: Specific views that are maybe for your more…

114
00:12:54.460 --> 00:13:03.769
Justice West: day-to-day activity of things you're doing every day, to save clicks to, like, actually do that. Some of that's gonna be, like, tips and tricks that Aaron shows at the end of this call.

115
00:13:03.960 --> 00:13:20.220
Justice West: And some of those may be, like, a dashboard or a workspace that we set up accordingly that kind of makes everything a little easier and kind of showing on screen. But, as of now, the philosophy overall is on these types of things, if it's… as long as it's not

116
00:13:20.280 --> 00:13:37.630
Justice West: like, the data elements you're seeing aren't wrong. For example, you may not use that, like, random out-of-the-box field there you see, like, asset or configuration item. Like, you may not use those at all, but we'll probably leave those there for the time being, and if there's other use cases where they pop up and we use them, that's great, and if not, we can eventually, you know.

117
00:13:37.770 --> 00:13:39.980
Justice West: Hide them, or move them out of the view.

118
00:13:41.620 --> 00:13:42.830
Justice West: Sorry, Aaron.

119
00:13:44.040 --> 00:13:44.940
aaronbanister: All good.

120
00:13:45.150 --> 00:13:59.210
aaronbanister: I assume you're all familiar with these data elements, so we won't get too deep into it. Physician's apps, Radonc, and total providers. This total providers is just a calculation field that sums the three that are above it.

121
00:13:59.800 --> 00:14:02.909
aaronbanister: And… that's about it for an instance record.

122
00:14:04.970 --> 00:14:08.410
aaronbanister: So I'll head over back to the account for Utah.

123
00:14:08.930 --> 00:14:11.700
aaronbanister: And something else I wanted to show as well.

124
00:14:12.140 --> 00:14:17.340
aaronbanister: One thing that came up in, like, the initial design is it's not… it's not the best user experience to have to

125
00:14:17.610 --> 00:14:21.369
aaronbanister: Click and drill into this instance to see this information.

126
00:14:21.480 --> 00:14:24.180
aaronbanister: So there's things that you can do to simplify that.

127
00:14:24.590 --> 00:14:38.420
aaronbanister: Most of the time where you're on a list view like this, you'll see this gear icon, and you can click on that to show and hide different columns, and this pertains to you and your specific, user. So if I wanted Radonk.

128
00:14:38.680 --> 00:14:44.650
aaronbanister: physicians, APPs, total providers all to show up in the list, I can just

129
00:14:44.970 --> 00:14:47.850
aaronbanister: Throw those down in the selected column.

130
00:14:48.120 --> 00:14:52.640
aaronbanister: And it'll refresh, and now it's actually going to show me those numbers.

131
00:14:52.940 --> 00:14:57.250
aaronbanister: Without drilling in, just as an example of how you can surface information.

132
00:15:00.080 --> 00:15:07.859
aaronbanister: Alright, so we've covered an account, we've covered account team members and instances. Do you have any questions so far before I get into the next two tabs?

133
00:15:09.880 --> 00:15:19.779
Susan Esary: So, I have two quick questions, Erin. So, when you're on the, account team members, how would you edit those? Would you just click on the name and then choose someone else? Is that how that works?

134
00:15:19.890 --> 00:15:21.060
aaronbanister: Yes.

135
00:15:21.060 --> 00:15:25.180
Susan Esary: Barry is not the correct user, just click on the name and assign someone else.

136
00:15:25.350 --> 00:15:38.019
aaronbanister: You can actually just double-click the empty space. Well, there's a security ACL blocking it. This little icon over here, the eye icon, is how you could click into this specific line item.

137
00:15:38.130 --> 00:15:40.020
aaronbanister: And I just opened it in a new tab.

138
00:15:40.460 --> 00:15:52.040
aaronbanister: And this is… this is all that looks like. This is really just a relationship between an account and a user, and it's defining what that relationship responsibility is. So yes, you would just come in here and change this to somebody else.

139
00:15:54.430 --> 00:15:59.900
Susan Esary: And then my second question was, when you were adding those different elements, with that drop-down.

140
00:16:03.530 --> 00:16:06.120
Susan Esary: I just was looking for one. Okay.

141
00:16:06.500 --> 00:16:10.200
Susan Esary: So, Tom, I don't see the clinic code there. Is that one we're going to be adding?

142
00:16:10.730 --> 00:16:12.310
Susan Esary: I see clinic ID.

143
00:16:12.310 --> 00:16:13.929
aaronbanister: Is it a short code by chance?

144
00:16:13.930 --> 00:16:15.219
Salena Reeves: tab, look above it.

145
00:16:15.940 --> 00:16:17.790
Salena Reeves: There was a different tab that showed it.

146
00:16:19.310 --> 00:16:20.610
Susan Esary: The clinic code?

147
00:16:20.610 --> 00:16:22.290
Salena Reeves: Yeah, what was it.

148
00:16:22.680 --> 00:16:23.190
Heather Chase: Tuesday.

149
00:16:23.400 --> 00:16:26.060
Suchaya Laddaphan: abbreviation, Aaron.

150
00:16:26.060 --> 00:16:27.900
Susan Esary: Is that the same as the clinic code?

151
00:16:27.900 --> 00:16:29.560
Heather Chase: I think she's looking for the number.

152
00:16:29.760 --> 00:16:31.970
Susan Esary: No, we had the number, that's the clinic ID.

153
00:16:31.970 --> 00:16:36.839
Salena Reeves: Yeah, it's the… they're calling it the assumed name on this thing for some reason.

154
00:16:36.890 --> 00:16:38.449
Susan Esary: Oh, okay, gotcha, gotcha.

155
00:16:38.660 --> 00:16:41.200
Susan Esary: So the same name is the same as our clinic code.

156
00:16:41.750 --> 00:16:44.220
Salena Reeves: But when you talk about that, Cuz…

157
00:16:45.330 --> 00:16:50.540
Salena Reeves: assumes name could also be the non… legal name…

158
00:16:50.740 --> 00:16:51.999
Suchaya Laddaphan: Yeah, I think…

159
00:16:52.160 --> 00:17:07.079
Suchaya Laddaphan: when I did a crosswalk, the assumed name may be a nickname, field from the sales force, and then abbreviation that should be, like, you know, for example, Charlotte, OSC, right? And this one is Utah.

160
00:17:07.089 --> 00:17:08.329
Susan Esary: codes, yeah.

161
00:17:08.829 --> 00:17:09.849
Salena Reeves: Okay, so…

162
00:17:10.130 --> 00:17:10.630
Susan Esary: So, briefly.

163
00:17:10.630 --> 00:17:11.680
Salena Reeves: nickname…

164
00:17:11.680 --> 00:17:12.349
Susan Esary: Clinical.

165
00:17:12.359 --> 00:17:16.239
Salena Reeves: Pull it over, can we… we can update that, then, to be, like, what it's actually called?

166
00:17:16.240 --> 00:17:16.819
Tom McGovern: Yeah.

167
00:17:17.119 --> 00:17:19.579
aaronbanister: We can play with the labels, yep.

168
00:17:19.579 --> 00:17:20.309
Tom McGovern: I mean, with them.

169
00:17:20.520 --> 00:17:21.200
aaronbanister: Yeah.

170
00:17:21.359 --> 00:17:36.080
aaronbanister: That kind of reminds me, something that probably isn't in scope for this demonstration, but there is a contact-facing front-end portal where contacts can log in and follow the cases that they may submit. ServiceNow…

171
00:17:36.210 --> 00:17:55.920
aaronbanister: has a, an out-of-box registration code field right here that's specifically for providing access to the portal, and so that… this conversation reminded me that that's why this ended up with the abbreviation name, just so that it didn't conflict with this out-of-box code concept, but we can change the label if we need to.

172
00:17:56.890 --> 00:17:58.020
Susan Esary: Okay, great. Thank you.

173
00:17:58.020 --> 00:17:59.690
aaronbanister: Just for context on why.

174
00:18:00.360 --> 00:18:01.230
aaronbanister: Okay.

175
00:18:01.610 --> 00:18:03.169
Tom McGovern: We are not looking to have

176
00:18:03.700 --> 00:18:18.550
Tom McGovern: external people access this directly. For example, on the cases, as Melissa knows, and that's outside of this team, we work with the support team separately, but we're not looking for them to come in there and look at their cases or anything like that on the first phase. It's just going to be for internal view only.

177
00:18:18.550 --> 00:18:19.170
Salena Reeves: Okay.

178
00:18:19.420 --> 00:18:20.040
aaronbanister: Yes.

179
00:18:20.540 --> 00:18:32.259
Tom McGovern: We just want to make sure we get everything, the foundation set right before we start entertaining that idea, and then we want to be really careful, because we don't want to expose something that we have our own personal notes that we don't want external people to see for whatever reason, so…

180
00:18:32.700 --> 00:18:46.790
Tom McGovern: Aaron, can you show the activity, one of the other… outside of, like, install base, etc, and updating numbers, they take notes and stuff like that. Just explain to them the concept of the notes at the top, which is more of a pinned area you see at the very top of the screen for those who

181
00:18:46.810 --> 00:18:55.570
Tom McGovern: We went through this before, and then there's a notes section down below here under the Activities tab, where it keeps a running diary, if you could just explain that to them, because they do make notes on occasion.

182
00:18:56.110 --> 00:19:09.209
aaronbanister: Yep, you hit the nail on the head. This top one is more static. You can put whatever you need to in here, but as things change over time, and customers may, you know, choose a different EMR, or have, like, a specific…

183
00:19:09.210 --> 00:19:18.779
aaronbanister: arrangement setup that hasn't quite, come to fruition yet. You can, you can, you know, diary that out here in the notes section, just however you need to.

184
00:19:18.850 --> 00:19:30.689
aaronbanister: You'll just click into the box and add something, and then you hit post. It's kind of like social media feeling, almost. And you can see that if somebody else is on the record with you, it'll show you who that is and what they're doing.

185
00:19:31.220 --> 00:19:39.389
aaronbanister: Additionally, whenever you make changes to a field on this record, Like, if I say…

186
00:19:40.100 --> 00:19:42.100
aaronbanister: Let's change the registration code.

187
00:19:42.300 --> 00:19:55.680
aaronbanister: Most of those fields are tracked here as well. So you can see registration code was, or now is, UCSportal exclamation point, and you can see the old value as well, up beside the was part.

188
00:19:56.880 --> 00:19:59.410
aaronbanister: Does that make sense on notes activity?

189
00:19:59.860 --> 00:20:05.399
Salena Reeves: So, that… That represents all the activity and notes, so, like… Yes.

190
00:20:07.380 --> 00:20:08.769
Salena Reeves: I'm just trying to figure out…

191
00:20:08.880 --> 00:20:12.929
Salena Reeves: So, let's say that you've had a customer for multiple years.

192
00:20:13.510 --> 00:20:17.720
Salena Reeves: You're scrolling through 2 years' worth of notes to figure out where they changed that

193
00:20:18.500 --> 00:20:21.199
Salena Reeves: EMR or something, or is there a place to put…

194
00:20:21.200 --> 00:20:31.040
aaronbanister: Oh, if you're looking for something highly specific like that, you can filter, like, what was changed, so, like, you can just look at only EMR changes.

195
00:20:31.780 --> 00:20:33.250
aaronbanister: For instance, here. I mean…

196
00:20:33.250 --> 00:20:34.949
Justice West: what I would say the…

197
00:20:35.660 --> 00:20:42.189
Justice West: It would be kind of like a combination approach. So, think of the activity stream more as, like, quick notes and audit trail.

198
00:20:42.560 --> 00:21:01.930
Justice West: That you want to have for yourself. If you want to see, like, what their actual EMR is, like, obviously go to the EMR field. If you want to see when that EMR changed, you know, it would be through that method Aaron just showed by, like, filtering through the activity stream. So it just kind of depends on the specific example and what you're trying to do on how to do it.

199
00:21:04.150 --> 00:21:13.239
Justice West: And if any of you guys have any specific examples of, like, scenarios, feel free to bring those up, because we can chat through, like, what you would specifically do in that scenario.

200
00:21:15.080 --> 00:21:17.710
Justice West: Sorry, Aaron, keep moving forward.

201
00:21:18.250 --> 00:21:21.630
aaronbanister: Alright, we've got sold products up next, these…

202
00:21:21.890 --> 00:21:27.309
aaronbanister: Essentially represent the modules that are enabled on an account's instance.

203
00:21:28.550 --> 00:21:36.360
aaronbanister: Each of these has an activation date, which I'll use the same method to pull that in so we can see it without drilling in.

204
00:21:36.720 --> 00:21:41.560
aaronbanister: And we probably don't even need to see product, state, or quantity, so I'll just get rid of those.

205
00:21:42.490 --> 00:21:44.079
aaronbanister: Honestly, don't need that one either.

206
00:21:48.390 --> 00:21:50.140
aaronbanister: So you've got a list of, of…

207
00:21:50.280 --> 00:21:54.909
aaronbanister: modules and their activation dates. And you can click into these to see more information.

208
00:21:57.240 --> 00:21:59.250
aaronbanister: I clicked on Patient Engagement.

209
00:22:01.920 --> 00:22:12.870
aaronbanister: If I recall correctly, yeah, there's actually no, I didn't add any additional information here on these. This is just what you see is the name of a module and the activation date.

210
00:22:18.780 --> 00:22:21.880
Debbie Lindgren: I have a quick question regarding the products.

211
00:22:22.340 --> 00:22:29.020
Debbie Lindgren: I'm… Where would I find a termination date for a product?

212
00:22:32.220 --> 00:22:34.039
aaronbanister: Let's see.

213
00:22:34.040 --> 00:22:37.500
Justice West: Let me ask a… can I ask a follow-up question to you, Debbie?

214
00:22:37.650 --> 00:22:41.410
Justice West: Do you guys terminate specific modular…

215
00:22:41.720 --> 00:22:48.160
Justice West: Actually, better question. Are you contracting at the… Sold product slash module level.

216
00:22:48.620 --> 00:22:49.270
Debbie Lindgren: Yes.

217
00:22:49.600 --> 00:22:52.959
Justice West: Today, so, like, you would… Okay, so you would…

218
00:22:53.690 --> 00:22:58.440
Justice West: put in a different contract for care management versus patient engagement, right? Is what you're saying?

219
00:22:58.440 --> 00:23:02.399
Debbie Lindgren: So, no, they're all usually on the same contract, but…

220
00:23:02.400 --> 00:23:02.840
Justice West: Okay.

221
00:23:02.840 --> 00:23:04.080
Debbie Lindgren: There are amendments.

222
00:23:04.330 --> 00:23:10.940
Debbie Lindgren: Big, big example would be Texas now is only on Portal, where they had the full suite before.

223
00:23:11.060 --> 00:23:16.100
Debbie Lindgren: So… Gotcha. Management, symptom pathways, health checker, all that is terminated.

224
00:23:16.850 --> 00:23:17.580
Justice West: Catch up.

225
00:23:17.750 --> 00:23:28.239
Justice West: No, that's a good question. Erin, if you want to keep solutioning real-time, we can take this offline. I don't know that we have a good way to track that specifically.

226
00:23:28.650 --> 00:23:33.979
Justice West: But I don't… disagree, I think that would be a good field to have.

227
00:23:36.420 --> 00:23:39.020
Justice West: I don't disagree. I love speaking in double negatives today.

228
00:23:40.500 --> 00:23:44.919
aaronbanister: Servicenow does allow you to tie…

229
00:23:45.410 --> 00:23:50.719
aaronbanister: Contracts into sold products, and that contract could have

230
00:23:51.180 --> 00:23:55.749
aaronbanister: a termination date. Again, I don't know if that necessarily fits your specific use case, but…

231
00:23:56.140 --> 00:23:56.650
Justice West: I don't think it's

232
00:23:56.990 --> 00:24:03.620
Justice West: It does, and that's not… yeah, I was gonna say, that's not your fault, that's… I had that conversation with Debbie earlier in the day.

233
00:24:03.860 --> 00:24:08.120
Justice West: Let me talk to you offline. I have a couple ideas on how we could account for that.

234
00:24:08.440 --> 00:24:13.059
Justice West: And then you can tell me what the path of least resistance is from there.

235
00:24:13.630 --> 00:24:14.170
aaronbanister: True.

236
00:24:14.980 --> 00:24:19.190
Tom McGovern: And we have that on a data dictionary, Debbie, just so you know. We're tracking that world.

237
00:24:19.380 --> 00:24:32.969
Tom McGovern: The way I was seeing it was… oh, you go back to where you just were, open one of those up, where you'd open up, let's say, patient engagement, let's say they got rid of portal, you'd move the status from active to inactive, and then there'd be a termination date field to tell you exactly what day that happened on.

238
00:24:34.410 --> 00:24:35.950
Salena Reeves: An inactivation date?

239
00:24:36.300 --> 00:24:37.750
Tom McGovern: Yeah, exactly.

240
00:24:37.750 --> 00:24:45.200
Justice West: So, Aaron, if you save that, does that throw it in the history for this? That might be an easy way, if I can reference it in reporting, too.

241
00:24:46.160 --> 00:24:49.890
aaronbanister: This… this table will need to be audited, which we can.

242
00:24:49.890 --> 00:24:51.090
Justice West: And we'll turn that on.

243
00:24:51.090 --> 00:24:51.530
aaronbanister: Yeah.

244
00:24:51.530 --> 00:24:57.110
Justice West: Yeah. Okay, let's talk about that, but I think there's a couple easy paths to solutioning here that we could talk through.

245
00:24:57.910 --> 00:24:58.480
aaronbanister: Okay.

246
00:25:03.020 --> 00:25:09.119
aaronbanister: So, the last… data object to touch on is contracts. Let me go back to our accounts.

247
00:25:09.120 --> 00:25:16.859
Tom McGovern: Can you go back to accounts for a second? Just… I don't know if you have it built in here for, like, UUG, just show them, like, a parent-child relationship and how they would show up.

248
00:25:17.080 --> 00:25:22.429
Tom McGovern: We do that with the misfits, as I call them. This is a good example. We can see, like, the three children under there.

249
00:25:22.600 --> 00:25:23.230
aaronbanister: Particularly for.

250
00:25:23.230 --> 00:25:26.550
Tom McGovern: the people who are involved with UUG, and we have a couple other

251
00:25:27.010 --> 00:25:32.549
Tom McGovern: Examples in our customer database that we're tracking right now, but you'll see that's how you'd see the three different ones.

252
00:25:32.740 --> 00:25:40.320
Tom McGovern: And then the support team would put cases against the sub-ones, because the relationships are with the child accounts, not with the master account.

253
00:25:41.380 --> 00:25:42.319
Tom McGovern: Versus something like 10.

254
00:25:42.320 --> 00:25:42.710
Heather Chase: Excellent.

255
00:25:42.710 --> 00:25:58.409
Tom McGovern: But versus something like Texas, where the regions, we don't attack cases at the region level, but we created child accounts in Salesforce at the region level. As you saw there, we put all the items at the install base level for the regions, but Texas Oncology is just one account.

256
00:25:58.630 --> 00:26:17.470
Tom McGovern: And we're also trying to obviously marry up, as these accounts are used across all of one oncology, what's the best architecture for each of those, but Arizona would be another one, Susan. I don't have it here because I came in since then, but Arizona would be one we'd add as a child account to UUG when they go live, or right now we'd add them, so they'll come in.

257
00:26:20.210 --> 00:26:20.890
aaronbanister: Yep.

258
00:26:21.360 --> 00:26:22.570
aaronbanister: It's a good call-out.

259
00:26:27.810 --> 00:26:34.670
aaronbanister: Alright, let me find a good example where… I think this is the only one where a contract actually exists in test, maybe not.

260
00:26:40.000 --> 00:26:42.270
aaronbanister: Okay, it's on…

261
00:26:43.120 --> 00:26:48.560
aaronbanister: Oh, actually, I think I only have contracts in the dev instance, so we can… we can go through and just make one.

262
00:26:49.220 --> 00:26:51.019
aaronbanister: We'll go back to Utah, maybe.

263
00:26:53.880 --> 00:26:59.619
aaronbanister: The out-of-box use case for contracts is really, really simple.

264
00:27:00.090 --> 00:27:07.720
aaronbanister: They're not necessarily, like, forcing you to do anything too crazy here. All you need for a contract is to have it tied to an account.

265
00:27:07.880 --> 00:27:19.629
aaronbanister: And you can define administrators and approvers if you want to. I would recommend giving it some kind of a name for demonstration purposes. We can just call it something like General Software Agreement.

266
00:27:21.930 --> 00:27:26.670
aaronbanister: And then we can define a start date, and say that they're gonna start… The end of the month.

267
00:27:27.410 --> 00:27:28.380
aaronbanister: And save.

268
00:27:30.550 --> 00:27:41.220
aaronbanister: So now we have a contract record. Just at the bare minimum, you could upload, like, a PDF attachment to this, if they've already, signed paper.

269
00:27:41.430 --> 00:27:48.300
aaronbanister: And, this could be where you at least go in and look at the contract that's part of an account. So if we go back to the account.

270
00:27:49.130 --> 00:27:51.309
aaronbanister: You'll see that contract listed there.

271
00:27:55.850 --> 00:28:11.789
Tom McGovern: So, Justice, maybe you can just describe… I know you talked to Debbie earlier. We typically have not managed the contracts at the Salesforce level. People would go directly to Debbie, or Debbie will… her contract works now that stuff has moved across since the acquisition of Navigating Care… Navigating Cancer.

272
00:28:11.830 --> 00:28:28.099
Tom McGovern: just… maybe you and or Debbie can just give some thoughts on… we have account managers who'll go to Debbie and ask questions about contracts, Debbie will give them feedback, etc, but they don't typically… most people on this call outside of Debbie, don't have a construct of working with a contract directly within Salesforce today.

273
00:28:28.330 --> 00:28:42.129
Justice West: Yep, and Debbie and I had a great conversation. Debbie, if I speak out of turn, please correct me. But really, the reason it's in here is less because it was a firm requirement, we had to track it right in this spot.

274
00:28:42.290 --> 00:28:46.820
Justice West: More so, we're finalizing enhancements on the legal module.

275
00:28:47.060 --> 00:28:52.870
Justice West: That have seemingly drug out forever, but they're going to be in production very soon, like in the next couple weeks to month.

276
00:28:52.960 --> 00:29:04.810
Justice West: And that will allow just normal legal flow and process when the legal team is working on a ticket. There will be a contract output anyway, tied to the record. So nobody entering in any data, doing anything.

277
00:29:04.810 --> 00:29:16.899
Justice West: That's why it's there, because it's all kind of out of the box, you know, bigger picture process flow as a primary. Actually, but speaking to Debbie, I don't think, Tom, we have any desire to upload historical contracts in here.

278
00:29:17.370 --> 00:29:27.319
Justice West: And we'll just continue to leverage Contract Works as that source of truth, tracking, and if there's questions, or where Debbie's going. So that would live in Contractworks.

279
00:29:27.370 --> 00:29:38.640
Justice West: They're gonna filter in here via ServiceNow, anyway, so just kind of automatically, so they'll be in here for reference. If we need it, or we change our mind and we want to.

280
00:29:38.800 --> 00:29:41.999
Justice West: Use it for some workflows or something, but as of now.

281
00:29:42.190 --> 00:29:48.000
Justice West: I would mostly just ignore it. Debbie, does that sound right for everything we discussed?

282
00:29:48.000 --> 00:29:58.150
Debbie Lindgren: Yes, that's perfect. Sorry, I tried not to turn on my mic, because I have our gardener people here, and they're, like, using the leaf blower really, really loud.

283
00:29:58.150 --> 00:29:59.259
Justice West: No, yeah.

284
00:29:59.260 --> 00:29:59.780
Debbie Lindgren: It didn't win out.

285
00:29:59.780 --> 00:30:00.450
Justice West: Sorry.

286
00:30:00.920 --> 00:30:03.600
Tom McGovern: The noise cancellation's working good, Debbie, we can't hear anything.

287
00:30:03.600 --> 00:30:05.290
Debbie Lindgren: Okay, good.

288
00:30:05.310 --> 00:30:08.060
Heather Chase: Debbie, Oh, sorry, I'm sorry.

289
00:30:08.060 --> 00:30:08.650
Debbie Lindgren: Go ahead.

290
00:30:08.840 --> 00:30:14.719
Heather Chase: No, I was gonna say, in your discussions, with Justice and Aaron today, did you talk about the renewal date?

291
00:30:15.740 --> 00:30:20.669
Heather Chase: Because I don't see that anywhere. We do… Selena and I have to refer to that date a bit.

292
00:30:22.060 --> 00:30:30.750
Debbie Lindgren: We did not, and I know that was in the mapping with, you know, in Tom's spreadsheet. I know we had that. I don't know where it is.

293
00:30:31.280 --> 00:30:33.030
Tom McGovern: You know, we put on the contracts tab.

294
00:30:33.030 --> 00:30:38.109
Justice West: It would probably be on the contract. I can just put that placeholder date there, Debbie, so you're not having to go in and

295
00:30:38.250 --> 00:30:41.900
Justice West: necessarily reference it. We can, I can move it elsewhere.

296
00:30:42.450 --> 00:30:43.070
Justice West: we can do.

297
00:30:43.070 --> 00:30:50.669
Debbie Lindgren: So it would be here in this screen, and, like, if you would type, click on the gear thing, you could put that on here, is that…

298
00:30:50.670 --> 00:30:56.430
Tom McGovern: Yes, yeah, if you keep at the contracts level, if you… based on your conversation.

299
00:30:56.660 --> 00:30:58.540
Tom McGovern: On that part of the world there.

300
00:30:59.490 --> 00:31:11.150
Justice West: Again, with… it should… well, let me ask you this dumb question. Is renewal date, I assume, is different than the end date? Because that's when you want to, like, get a renewal done, is that what I remember?

301
00:31:12.140 --> 00:31:19.899
Debbie Lindgren: Yeah, it's just… they renew annually, automatically, unless there's a termination notice. And so.

302
00:31:20.080 --> 00:31:33.749
Debbie Lindgren: that… it's basically a month and a date, not really a year so much, because it's just every year it renews, so no one really should have to go in there and make a change, as that's manual. But,

303
00:31:34.220 --> 00:31:40.550
Debbie Lindgren: You know, something like, If it started on 4-1, then 4-1, every year, it renews.

304
00:31:41.640 --> 00:31:43.710
Debbie Lindgren: That's what she needs, you know.

305
00:31:44.280 --> 00:31:45.189
Justice West: That makes sense.

306
00:31:45.190 --> 00:31:54.640
Heather Chase: Is that the case? I didn't realize that was… oh, I thought I've come across some, that the dates were because they signed an amendment and then their date changed.

307
00:31:55.000 --> 00:31:55.949
Heather Chase: Everything's time.

308
00:31:55.950 --> 00:32:07.230
Debbie Lindgren: That happens too, right? Yeah. Like, just now, Michiana just signed an amendment that changed their… their year-end date. It's a 3-year now, so…

309
00:32:10.780 --> 00:32:12.420
Debbie Lindgren: So anyway, yeah, it's…

310
00:32:14.000 --> 00:32:20.489
Tom McGovern: If we decide we're not gonna use the contracts tab, then we're gonna move it. We need to find another place for the home, based on your conversation with Debbie.

311
00:32:21.230 --> 00:32:24.349
Justice West: Yep, and that'll… that would be easy to do either way.

312
00:32:24.890 --> 00:32:35.539
Tom McGovern: Because right now it's mapped over to that contracts tab based upon earlier work, and it had that renewal date field. It's a full date, but as Debbie says, it's typically just the month and the year, but we have month, year, and day.

313
00:32:36.430 --> 00:32:37.160
Justice West: Okay.

314
00:32:38.280 --> 00:32:41.309
Justice West: Aaron, let me and you talk through that,

315
00:32:42.840 --> 00:32:47.259
Justice West: When we work on this. I'm making a little… we're making a little list. I don't know if

316
00:32:47.570 --> 00:33:00.250
Justice West: we have AI, dictation here, and from the recording as well, but we'll take the… anything we continue to come up with, the… everything that's been called out so far, like, tiny little things that'll be super easy, so…

317
00:33:00.730 --> 00:33:02.890
Justice West: Shouldn't disrupt any timelines or anything.

318
00:33:04.580 --> 00:33:05.600
aaronbanister: Okay.

319
00:33:05.820 --> 00:33:08.640
aaronbanister: That really wraps up the…

320
00:33:08.810 --> 00:33:13.260
aaronbanister: The data model portion of the… of the demonstration.

321
00:33:13.600 --> 00:33:27.409
aaronbanister: So, if there are any more questions, anybody, you can feel free to unmute and ask. The only part that I have outstanding on the agenda is just basic, like, user interface tips and tricks within ServiceNow.

322
00:33:29.610 --> 00:33:30.010
Tom McGovern: I'll just…

323
00:33:30.010 --> 00:33:31.200
aaronbanister: your experience.

324
00:33:31.610 --> 00:33:47.940
Tom McGovern: I'll just add, everything we need to do as a business should be able to be handled by each of you. No, it takes some learning curve, and Sashai and I will be your right-hand partners for that to happen, and take feedback back to the teams. You're more than welcome to take it back to Aaron and Justice if you need to, but we'll be your liaisons to keep you guys close with.

325
00:33:48.130 --> 00:33:58.939
Tom McGovern: there shouldn't be anything that you need to have put a ticket into the ServiceNow team in order. You should have all your permissions to be able to make any changes to do your needs. Add accounts, edit accounts.

326
00:33:59.080 --> 00:34:06.469
Tom McGovern: Changed what their provider counts are on their install base items, changed contact information, add notes, everything we went through today.

327
00:34:06.620 --> 00:34:21.720
Tom McGovern: there's nothing in here that we've seen working on it with the team at One Oncology, or on OneOncology, that… anything that's being restricted from you today. Not making promises, as this being used more fundamentally across the whole organization, I could see sometimes that there are going to be more

328
00:34:21.820 --> 00:34:36.200
Tom McGovern: restrictive on accounts. I did that at companies I worked at before with thousands and thousands of people, but for right now, you guys should have a capability to make the changes you need to do in order to be successful. And if you don't, obviously let us know, but there shouldn't be anything restricting you.

329
00:34:39.469 --> 00:34:55.009
Tom McGovern: One of the things we want to do is have you put a ticket in. Let's say you want to change the number from 15 apps mid-levels to 22. We don't want you to have to put a ticket in and have to wait 3 or 4 days or longer for somebody on the team to be able to give you permissions or give that… be able to make that change happen on your behalf, so…

330
00:34:55.389 --> 00:35:00.669
Tom McGovern: Good thing is there that you guys should have all the capabilities you do in Salesforce… in ServiceNow that you have in Salesforce today.

331
00:35:02.290 --> 00:35:03.359
Heather Chase: Thank you.

332
00:35:03.690 --> 00:35:08.250
Salena Reeves: Is there a way to… Link emails to it, too, so you've got a history.

333
00:35:08.470 --> 00:35:13.090
Salena Reeves: You have interactions with the… Customer?

334
00:35:13.760 --> 00:35:17.980
aaronbanister: Would those be separate from, like, just case management cases?

335
00:35:18.390 --> 00:35:19.030
Salena Reeves: Yes.

336
00:35:19.580 --> 00:35:23.969
Salena Reeves: Because there's gonna be conversations that the account managers or other people might be having with.

337
00:35:25.470 --> 00:35:26.490
aaronbanister: That's a good question.

338
00:35:26.990 --> 00:35:32.929
aaronbanister: Note that down for, research, justice, if you don't mind.

339
00:35:32.930 --> 00:35:37.230
Tom McGovern: And in Phase 1, Selena, so it just requires to get slide, but what do you think?

340
00:35:37.430 --> 00:35:37.930
Tom McGovern: Well, here'.

341
00:35:37.930 --> 00:35:38.380
Justice West: Good talk.

342
00:35:38.380 --> 00:35:42.300
Tom McGovern: You know, she wants to be able to have a conversation back and forth with a customer account.

343
00:35:42.300 --> 00:35:45.810
Salena Reeves: No, I am not. No, no, no, no, no, no, no, no, no, no, don't make it difficult.

344
00:35:47.090 --> 00:35:49.860
Salena Reeves: documentation, This is great knowledge.

345
00:35:49.860 --> 00:35:50.630
Tom McGovern: Oh, by one.

346
00:35:50.630 --> 00:35:56.040
Salena Reeves: you've seen people come and go at companies, and all of a sudden, I inherit you know.

347
00:35:56.040 --> 00:35:57.040
Tom McGovern: I'm with ya.

348
00:35:57.290 --> 00:36:12.860
Salena Reeves: you know, Texas Oncology, let's say, Melissa's on vacation, and I… they're saying, oh, well, they told me you had this information, and I have no way of getting into Melissa's email, so I would go in here and look at the email history and go, oh, well, she sent that to you on the 3rd. Here, let me get this information for you.

349
00:36:14.770 --> 00:36:15.380
Justice West: They put that information.

350
00:36:15.380 --> 00:36:17.750
Tom McGovern: in here, it's cut and pasted in the sales…

351
00:36:17.750 --> 00:36:19.880
Salena Reeves: No, that we link our emails…

352
00:36:20.140 --> 00:36:26.260
Salena Reeves: So that it puts a blind carbon copy into Salesforce, so you've got a historical document of those

353
00:36:26.380 --> 00:36:29.090
Salena Reeves: Emails that were sent to them and the responses they sent.

354
00:36:29.090 --> 00:36:29.999
Tom McGovern: We can do that today.

355
00:36:30.000 --> 00:36:36.680
Melissa Alexander: Yeah, I did it for… I did it for sales leads. I would BCC the,

356
00:36:36.890 --> 00:36:41.200
Melissa Alexander: The account, so that any correspondence would be in there?

357
00:36:42.530 --> 00:36:43.429
Tom McGovern: I gotcha now.

358
00:36:43.430 --> 00:36:43.950
Melissa Alexander: Yeah.

359
00:36:44.140 --> 00:36:47.239
Tom McGovern: And it's like a unique link that knows it goes directly to that account when.

360
00:36:47.240 --> 00:36:47.650
Melissa Alexander: Correct.

361
00:36:47.650 --> 00:36:49.450
Tom McGovern: by Salesforce. Yeah.

362
00:36:49.450 --> 00:36:51.669
Melissa Alexander: But I… I don't use that for.

363
00:36:51.670 --> 00:36:52.710
Tom McGovern: Pretty unique email address.

364
00:36:52.710 --> 00:36:53.280
Melissa Alexander: Right.

365
00:36:54.250 --> 00:36:55.260
Melissa Alexander: Yeah.

366
00:36:55.640 --> 00:37:06.130
Justice West: Tom, we can talk through it, but the short version is, like, can we do something like that? Yes. It's more like timelines and phases and all that fun conversation to have.

367
00:37:06.130 --> 00:37:06.650
Tom McGovern: Yep.

368
00:37:07.520 --> 00:37:08.440
Justice West: But…

369
00:37:09.230 --> 00:37:16.830
Justice West: I can think of a couple ideas right off. I'd obviously want Aaron to validate them, and not just me running off all assumptions, but I think we could.

370
00:37:18.030 --> 00:37:27.079
Tom McGovern: Yeah, well, I'm here at Selena's station. We want an easy way to be able to transfer email conversations to this account record in ServiceNow. Fair enough, Selena?

371
00:37:27.080 --> 00:37:29.749
Salena Reeves: It's just a way to document some of the history that's not…

372
00:37:29.750 --> 00:37:30.420
Tom McGovern: Right.

373
00:37:31.220 --> 00:37:45.710
Justice West: And I guess from when we do some solutioning there, can you give me examples of when… because I would imagine that, like, you would… from what Melissa was saying, not every single thing is BCC'd. It would be important things, or more relevant, does that sound right?

374
00:37:46.540 --> 00:37:47.270
Melissa Alexander: Yeah.

375
00:37:47.480 --> 00:37:48.280
Melissa Alexander: Yep.

376
00:37:48.280 --> 00:37:55.830
Justice West: So, can you give me, like, a specific example I can use when I'm solutioning of when you would want it to flow in here, a type of conversation, that kind of thing?

377
00:37:55.830 --> 00:38:16.520
Melissa Alexander: You know, something might be a… if we use Texas as an example, it would be ideal for me to share maybe the monthly meeting notes with, you know, the broader team and also the executive team, so that if, you know, we need to do a review to find out what was proposed or discussed, you know, at a certain time, I think those would be

378
00:38:16.520 --> 00:38:22.990
Melissa Alexander: you know, some key emails that I would want to see in Stored in, serviceNow.

379
00:38:23.650 --> 00:38:24.240
Justice West: Okay.

380
00:38:24.470 --> 00:38:25.070
Melissa Alexander: Mount.

381
00:38:25.070 --> 00:38:26.640
Justice West: So, okay.

382
00:38:26.640 --> 00:38:39.460
Melissa Alexander: To Selena's point, if somebody has to go back, if I'm not in the office, or if, you know, if I wasn't here anymore, they could go in and see, like, what was discussed previously, you know, by the account owner.

383
00:38:40.200 --> 00:38:41.300
Justice West: Sure, okay.

384
00:38:44.560 --> 00:38:45.820
Justice West: Thank you very much.

385
00:38:46.640 --> 00:38:47.310
Melissa Alexander: Sure.

386
00:38:49.420 --> 00:38:54.300
aaronbanister: Alright, do you want to move on to the quick UI tips and tricks section before we wrap up?

387
00:38:54.840 --> 00:39:10.460
aaronbanister: Okay, so there's two things, it's really just two problems that I'm going to solve with these tips, and these are present for every new ServiceNow user's first time in ServiceNow. I don't know why it's like this, because it'd be so easy for them to make it not like this.

388
00:39:10.510 --> 00:39:18.350
aaronbanister: But, essentially, the first problem is this. You're navigating in ServiceNow, you find a record you want to look at, and you want to open it in a new tab.

389
00:39:18.520 --> 00:39:21.590
aaronbanister: That's great. It's open a new tab. But now…

390
00:39:22.040 --> 00:39:28.869
aaronbanister: all of my navigation is gone, and I just have this one record. So, I can't get anywhere else from here, really.

391
00:39:29.020 --> 00:39:31.410
aaronbanister: This is a user preference.

392
00:39:31.660 --> 00:39:35.829
aaronbanister: That you can override by clicking on your profile icon in the top right corner.

393
00:39:36.500 --> 00:39:37.640
aaronbanister: Preferences.

394
00:39:38.870 --> 00:39:42.250
aaronbanister: Display, and always show top navigation.

395
00:39:43.790 --> 00:39:50.840
aaronbanister: Now, when I refresh, the next time that I do the same thing, if I open this in a new tab.

396
00:39:51.020 --> 00:39:56.489
aaronbanister: My top navigation is retained, and I can still navigate elsewhere in the system.

397
00:39:57.140 --> 00:39:58.320
aaronbanister: So that's number one.

398
00:39:59.360 --> 00:40:06.810
aaronbanister: The second user experience improvement is you can give yourself a custom sidebar navigation.

399
00:40:07.000 --> 00:40:09.010
aaronbanister: By setting favorites.

400
00:40:09.290 --> 00:40:13.019
aaronbanister: So, I showed you how to navigate to the accounts table.

401
00:40:13.180 --> 00:40:16.199
aaronbanister: By using the all search, and now we're here.

402
00:40:16.360 --> 00:40:18.979
aaronbanister: But if we wanted to favorite this.

403
00:40:19.000 --> 00:40:37.679
aaronbanister: you know, ignore my existing favorites and just pretend this was an empty menu. You'd click on the favorites tab, and, you could just click on a favorite, and it would take you right there. That's not, like, a difficult concept or anything. But to add favorites, once you're where you want, then you just come up here to this little center pill menu and press the star icon.

404
00:40:38.080 --> 00:40:41.400
aaronbanister: And hit done. Now there's a favorite in here for that.

405
00:40:41.780 --> 00:40:43.620
aaronbanister: But you can take it one step further.

406
00:40:43.870 --> 00:40:50.939
aaronbanister: and click this thumbtack menu to pin it to your sidebar. So now these options are always just, you know, one click away.

407
00:40:51.600 --> 00:40:59.479
aaronbanister: If you get to the point where you have several favorites sort of muddying up the view, you can click this pencil icon to edit them.

408
00:40:59.730 --> 00:41:01.889
aaronbanister: And you can create a custom group.

409
00:41:02.750 --> 00:41:04.939
aaronbanister: I can call this one Navigating Care.

410
00:41:05.890 --> 00:41:08.990
aaronbanister: And then you can drag things into that group.

411
00:41:09.540 --> 00:41:13.729
aaronbanister: So now accounts is inside the Navigating Care group.

412
00:41:13.870 --> 00:41:16.820
aaronbanister: And you can expand and collapse.

413
00:41:17.580 --> 00:41:19.849
aaronbanister: Those little submenus, just like that.

414
00:41:24.430 --> 00:41:29.949
Tom McGovern: Are those all personalized for you, and is there a way to create a group that's available to all everybody that logs in?

415
00:41:30.140 --> 00:41:39.700
Tom McGovern: in the Navigating Care Team, for example, I could see I'd like to create a group that says accounts for Heather, and accounts for Selena, and accounts in implementation.

416
00:41:39.810 --> 00:41:59.129
Tom McGovern: And I could immediately go there and go, okay, one, I can remember which accounts that they have without me having to refer to the spreadsheet, which I do, on Google Drive, I've bookmarked there, and obviously the ones that it's easier for them to navigate to, whether it's Kristen or Dana, or for the implementation one, see all the ones that are in implementation, really easy, go right to it.

417
00:41:59.170 --> 00:42:06.580
Tom McGovern: Or, in that case, Heather or Selena can go right in, make an update for Debbie without having to go to the search, and they can just look at their accounts listed here and go that way.

418
00:42:07.090 --> 00:42:22.740
aaronbanister: The short answer is yes, you can set up favorites that are filtered like that. The tricky part is just finding the right filter and the right table to filter. So if you were trying to approach it from the angle of who manages the account, or supports it.

419
00:42:22.980 --> 00:42:32.409
aaronbanister: your favorite might be one of these account team member records. So if I go to just account team members in general.

420
00:42:32.830 --> 00:42:40.999
aaronbanister: And we can see, alright, show me all the accounts where the account owner is Heather Chase.

421
00:42:42.290 --> 00:42:48.999
aaronbanister: I filtered that by right-clicking one of these elements and clicking Show Matching. That automatically built my filter, so now we're seeing

422
00:42:49.040 --> 00:43:03.979
aaronbanister: All account team members whose responsibility is account owner and whose user is Heather Chase. And since this is a related list, or a many-to-many relationship table, we're seeing many instances of Heather related to many different accounts.

423
00:43:04.110 --> 00:43:10.100
aaronbanister: So we could, in theory, favorite this, and just call this… Heather's accounts…

424
00:43:11.970 --> 00:43:15.610
aaronbanister: And we… we can add this to the Navigating Care Group.

425
00:43:16.290 --> 00:43:20.090
aaronbanister: And we can get back to it pretty quickly.

426
00:43:20.090 --> 00:43:21.810
Salena Reeves: Sexy. We could do that.

427
00:43:21.810 --> 00:43:23.200
Heather Chase: Really nice.

428
00:43:23.200 --> 00:43:29.640
Salena Reeves: We could do that for our own views, we could do that for EMRs, we could do that for… okay, that is sexy.

429
00:43:31.050 --> 00:43:31.780
aaronbanister: There you go.

430
00:43:32.890 --> 00:43:43.059
aaronbanister: Yeah, ServiceNow has a lot of, like, very nice quality of life enhancements just like that. The tricky part is just understanding where to look and how to build your queries.

431
00:43:43.420 --> 00:43:47.099
aaronbanister: But we can obviously help out with that anytime you guys have ideas.

432
00:43:47.360 --> 00:43:48.600
aaronbanister: For such things.

433
00:43:53.210 --> 00:44:01.320
Tom McGovern: renewal dates coming up, too, Selena. I know Debbie would like that one, too, as well. You guys can see, okay, I got this one coming up, it's in its renewal date, etc.

434
00:44:02.610 --> 00:44:03.750
Tom McGovern: Were you gonna say something?

435
00:44:03.750 --> 00:44:09.279
Heather Chase: I was just gonna say, in Monday, all of our stuff's moving over, or perform up by Monday?

436
00:44:10.190 --> 00:44:28.020
Tom McGovern: Yeah, I took a snapshot of it yesterday when Tachaya sent that note out on Tuesday, yesterday, I think it was, or Monday night, and so I have a snapshot of all of it. So if you need to make a change since then, just let me know. I will keep it in sync, and I was going to catch up with you guys tomorrow and Friday, all the way up until go-live date, just to make sure if there's anything that's pressing over the next 3 days.

437
00:44:30.700 --> 00:44:37.470
Tom McGovern: I know you guys don't make changes that often, but I just want to make sure that… I'm going to write a reconciliation report on the provider accounts for Debbie.

438
00:44:37.710 --> 00:44:45.369
Tom McGovern: on Monday, to make… whenever we get everything out loaded in production, to make sure what shows in Salesforce is what's showing in ServiceNow, to make sure that

439
00:44:45.520 --> 00:44:49.020
Tom McGovern: Everything reconciles and there's no surprises when we get closer to the month end.

440
00:44:50.010 --> 00:44:50.979
Heather Chase: Thank you.

441
00:44:50.980 --> 00:44:54.880
Salena Reeves: So, would all of the stuff that we usually do through reporting now to get

442
00:44:55.530 --> 00:45:03.109
Salena Reeves: those views and filters in Salesforce be done through filters here, or do we have the ability to build out reports and have them automated?

443
00:45:05.180 --> 00:45:08.549
aaronbanister: You do have the ability to build reports.

444
00:45:08.840 --> 00:45:24.119
aaronbanister: that's a totally separate module within ServiceNow that we can go over sometime, because it's kind of its own beast, but that's sort of ServiceNow's bread and butter. You set up a really good data model, like we have here, and you can get really good granular reporting.

445
00:45:26.480 --> 00:45:29.579
aaronbanister: I can probably just show you, like, an example if you want to see one.

446
00:45:30.560 --> 00:45:35.640
aaronbanister: Do you know of any good example dashboards, Justice, that would be good to… show off here.

447
00:45:36.110 --> 00:45:43.360
Justice West: If you go to Dashboards, go to maybe… search for CPO.

448
00:45:45.760 --> 00:45:48.849
Justice West: I don't know if that's gonna be a good… it's not gonna be in your recents.

449
00:45:49.200 --> 00:45:54.090
Justice West: I don't know if this would be a good one, there's just one I know that's populated a lot, Nick has a lot that are populated.

450
00:45:54.970 --> 00:45:58.430
Justice West: I don't know a good dashboard view that's for, like.

451
00:45:58.980 --> 00:46:02.829
aaronbanister: That's a good example, though. This shows a few of the different reports.

452
00:46:02.830 --> 00:46:03.180
Justice West: I'm gonna…

453
00:46:03.180 --> 00:46:04.020
aaronbanister: Perfections.

454
00:46:04.020 --> 00:46:04.560
Justice West: you.

455
00:46:06.640 --> 00:46:14.330
aaronbanister: This is a really granular and detailed chart, and it showcases how granular you can get.

456
00:46:18.270 --> 00:46:23.319
Tom McGovern: And Melissa, we're gonna do something like that for cases, to give you that dashboard look that

457
00:46:23.570 --> 00:46:28.180
Tom McGovern: Gives you much more insight than you have currently today in Salesforce, so just an FYI.

458
00:46:28.180 --> 00:46:28.970
Salena Reeves: Oh, really?

459
00:46:28.970 --> 00:46:30.369
Tom McGovern: Yeah, for Selena's question.

460
00:46:30.370 --> 00:46:32.400
Heather Chase: Dashboards are the bomb.

461
00:46:32.550 --> 00:46:33.300
Tom McGovern: For that portion.

462
00:46:33.300 --> 00:46:33.920
Heather Chase: Great.

463
00:46:34.590 --> 00:46:38.969
Tom McGovern: And obviously, for you guys in account management, if you want to see what's going on, if you have questions with your customers.

464
00:46:39.110 --> 00:46:41.069
Heather Chase: Are we gonna be able to build our own dashboards?

465
00:46:41.790 --> 00:46:43.550
Justice West: Your… can?

466
00:46:43.840 --> 00:46:44.400
Heather Chase: Okay.

467
00:46:45.430 --> 00:47:02.090
Justice West: And we'll show you how to do that. Debbie was actually asking about that, too. All… we'll give you guys access to build all your own reports, which then you could build your own… dashboards, all they are is just a little concatenation of the different reports, kind of put together in a visual.

468
00:47:02.170 --> 00:47:06.740
Justice West: So, if you can build reports, you can build dashboards, and you'll be good to go.

469
00:47:07.420 --> 00:47:09.310
Heather Chase: Awesome. Thank you.

470
00:47:10.100 --> 00:47:10.980
Salena Reeves: That's exciting!

471
00:47:10.980 --> 00:47:14.299
Melissa Alexander: Can I… can I still have reports?

472
00:47:14.990 --> 00:47:16.149
Melissa Alexander: Okay, good.

473
00:47:16.270 --> 00:47:25.780
Melissa Alexander: Because I… some reports, I really like that detail, and I take them and pull them out into Excel and stuff, but I mean, the dashboards are nice, but…

474
00:47:26.180 --> 00:47:27.449
Melissa Alexander: In some cases.

475
00:47:28.210 --> 00:47:32.309
Tom McGovern: You know, you share them with your team, or share them with your… Michael, or whoever else, exactly.

476
00:47:32.520 --> 00:47:33.150
Melissa Alexander: Yeah.

477
00:47:33.150 --> 00:47:35.230
Tom McGovern: Play with the performances of the team. Yep.

478
00:47:36.360 --> 00:47:37.990
Melissa Alexander: Thanks.

479
00:47:40.630 --> 00:47:43.870
Tom McGovern: Okay, so for next steps, we're looking to… oh, go ahead, Erin.

480
00:47:44.090 --> 00:47:47.820
aaronbanister: No, you're good. I was just gonna say, that concluded my agenda, so you can take over.

481
00:47:47.820 --> 00:47:54.009
Tom McGovern: All right, so next steps, we are going to load the data that we took a snapshot in Salesforce into

482
00:47:54.270 --> 00:48:00.409
Tom McGovern: Servicenow. We'll have it live. Our goal is to have it live on Monday. If anything you need… if it changes before then.

483
00:48:00.580 --> 00:48:05.520
Tom McGovern: Hold on to them, and or let me know, and I will keep it in reconcile, so any changes that you guys have.

484
00:48:05.700 --> 00:48:22.030
Tom McGovern: I'll go into Sales ServiceNow once Aaron says we're all loaded up to make those changes for you, so we can have it all there. Debbie, I'll do the reconciliation and compare it against what Salesforce has now. I know that report you run currently. I'll reconcile the numbers there to make sure there's no surprises and nothing gets lost in the transition.

485
00:48:22.280 --> 00:48:30.949
Tom McGovern: So Chai and I will follow up with all you guys on, one, making sure you can log in and you followed along, making sure these tips and tricks about the navigation are there.

486
00:48:30.980 --> 00:48:44.830
Tom McGovern: And then we'll be staying in touch with you at least once or twice a week, just to check in to make sure that you're not having questions, or there's any feedback you want to give us in terms of how to do some more fit and finish work, changing labels, you get confused on where to find a field.

487
00:48:44.830 --> 00:48:51.220
Tom McGovern: will help you reconcile that over the next many, many weeks. And then our goal is to transition that

488
00:48:51.460 --> 00:48:55.389
Tom McGovern: to the cases and bring on the support team on the 1st of April.

489
00:48:55.770 --> 00:49:10.780
Tom McGovern: If we get everything built that's necessary for that part of the world there. So we want to set that foundation over the next couple weeks with the accounts to get them in good shape so there's no surprises. We have all the accounts, we don't miss any, and then bring on the support team after that. And then, obviously, we're doing

490
00:49:10.890 --> 00:49:18.000
Tom McGovern: as we said, this is the first step. They set the foundation for much better improvements on there. I know that for… Melissa wants to do some really

491
00:49:18.430 --> 00:49:34.689
Tom McGovern: for sophisticated workflow management inside of the cases that ServiceNow has to offer. We're talking about the emails on that part of the world, Selena. There's some stuff we want to build on top, but I first want to build that foundation piece and to get everybody comfortable with it, and then we can layer on some really cool new opportunities and

492
00:49:34.860 --> 00:49:37.630
Tom McGovern: enhancements and features that ServiceNow offers that

493
00:49:37.860 --> 00:49:55.190
Tom McGovern: Aaron and Justice talked to me about, and I said, wait, hold those off, tell the team after we get them, we get a good foundation in place. It sounds exciting, but we first want to just get that level, we want to overextend ourselves, and just take this over layer after layer as we build on top of it. So, that's the plan as we look out in the coming weeks and months.

494
00:49:56.700 --> 00:50:07.880
Suchaya Laddaphan: And just a quick note that, the access that you guys have right now is to the test environment, so I guess feel free to test it out through Friday, and then I think Tom and I will provide it

495
00:50:08.050 --> 00:50:12.849
Suchaya Laddaphan: provide you guys with more information regarding the Monday when we go live later this week as well.

496
00:50:13.070 --> 00:50:14.659
Justice West: Yeah, try to break it.

497
00:50:14.780 --> 00:50:15.570
Justice West: Try to break it.

498
00:50:15.570 --> 00:50:16.890
Suchaya Laddaphan: Yes.

499
00:50:17.100 --> 00:50:30.489
Kristin Olson-Celli: Challenge accepted. Yeah, I know Suchai and I like to try and break things. Or Selina, I was gonna say Selena, sorry. Is there a training guide, digital training guide?

500
00:50:31.190 --> 00:50:33.540
Kristin Olson-Celli: Or is… this is what we have?

501
00:50:34.110 --> 00:50:38.860
Justice West: Don't have one unless, Tom, you guys have been working on, but I was gonna try to put something together.

502
00:50:39.150 --> 00:50:58.130
Tom McGovern: Chyna, I've been working on a document for you, Kristen, which is, goes screen by screen to explain certain concepts behind that one, and we'll get that out to you, in addition to that we have what we have here on this recording as well. And then we'll be your right-hand partner, like I said earlier, on this, as you come up to speed. We also have somebody new starts, we want to give them a guide that they can ask.

503
00:50:58.650 --> 00:50:59.430
Kristin Olson-Celli: Thank you.

504
00:50:59.430 --> 00:50:59.970
Tom McGovern: Yep.

505
00:51:00.180 --> 00:51:01.190
Tom McGovern: Good question.

506
00:51:04.080 --> 00:51:06.120
Suchaya Laddaphan: Any other questions before we leave today?

507
00:51:09.340 --> 00:51:17.649
Suchaya Laddaphan: All right, Justice, Aaron, thank you all very much for your time today to walk us through, and thank you all for attending today. Bye-bye. Take care.

508
00:51:17.650 --> 00:51:18.880
Melissa Alexander: Thanks, bye.


---

# Meeting Summary

**Date:** March 18, 2026
**Attendees:** [[Aaron Banister (Me)|Aaron]] (presenter/ServiceNow admin), [[Justice West]] (ServiceNow product lead), Tom McGovern (Navigating Care), Suchaya Laddaphan (Navigating Care), Salena Reeves, Heather Chase, Susan Esary, Debbie Lindgren, Melissa Alexander, Kristin Olson-Celli

### Discussion

#### System Navigation & Getting Started
[[Aaron Banister (Me)|Aaron]] opened by walking the team through ServiceNow's backend interface. Access is via the ITIL Home button in OneID; a direct link was shared with Tom McGovern and Suchaya Laddaphan. He explained the core navigation pattern: the "All Search" bar to reach any module, list view as the default data display, and form view when clicking into a record. Create vs. modify flows are essentially identical across all tables — New button + form, then Submit (returns to list) or right-click Save (stays on record).

#### Accounts
Tom McGovern raised the practical concern about duplicate accounts: since Navigating Care comes in after contracts are signed, accounts should mostly already exist in ServiceNow, created automatically by legal-side automations. [[Aaron Banister (Me)|Aaron]] confirmed that in most cases manual account creation won't be needed — those automations are planned but not fully built yet. [[Justice West]] flagged a gap: how to convert an existing *Company* record into a customer *Account* (since accounts extend the core company table). This was acknowledged as something to cover in a follow-up. Salena asked about searching for potential duplicates; Aaron showed column-level wildcard search within the accounts table and noted the global search can be expanded to include companies and other objects.

#### Account Team Members
This data is now in a related list beneath the account (vs. directly on the account object in Salesforce). Susan Esary asked how to edit team members — Aaron demonstrated using the eye icon to open a record inline. Susan also flagged that she couldn't find a "Clinic Code" field; the team identified it as the "Assumed Name" field (which also stores the abbreviation, e.g., "OSC"). [[Aaron Banister (Me)|Aaron]] confirmed field labels can be changed.

#### Install-Based Items (Instances)
These are now separate from the account object, representing individual customer instances. [[Aaron Banister (Me)|Aaron]] walked through a Utah example. He demonstrated customizing the list view via the gear icon to surface Radonc, Physician Apps, APPs, and Total Providers columns inline — eliminating the need to drill into each record. [[Justice West]] noted the current philosophy is to leave out-of-box fields visible while the team gets familiar with the structure, hiding them later if they're not useful.

#### Sold Products (Modules)
These represent active modules on an account's instance. Debbie Lindgren raised a key gap: there's currently no termination date field, and her team needs to track when modules are dropped (e.g., Texas Oncology went from full suite down to Portal only). Tom McGovern proposed adding an active/inactive status toggle + termination date field. [[Justice West]] and [[Aaron Banister (Me)|Aaron]] agreed to solution this offline — likely by enabling auditing on the sold products table plus adding the status/date fields. Tom confirmed the renewal date is already in the data dictionary/mapping.

#### Contracts
[[Aaron Banister (Me)|Aaron]] demonstrated the basic contract structure (name, account link, start/end date, attachment support). [[Justice West]] clarified context: contracts will flow in automatically from the legal module, which is days-to-weeks from production. The team does not intend to backfill historical contracts — ContractWorks remains the source of truth. Heather Chase raised the renewal date question; Debbie explained renewals are auto-annual (same month/day each year) unless a termination notice is given. [[Justice West]] committed to placing the renewal date field as a placeholder.

#### Notes & Activity Stream
Tom asked Aaron to explain the two-tier notes model: the static top Notes field (for persistent context) vs. the Activities tab (running diary + field-change audit trail). Salena asked whether the activity stream could be filtered — Aaron confirmed yes, including filtering to see only changes on a specific field (e.g., only EMR changes). [[Justice West]] framed it as "quick notes and audit trail."

#### Parent-Child Account Hierarchy
Tom requested a live demo. UUG is the example with three child accounts — cases should be logged against the child accounts, not the parent. Texas Oncology is structured differently: one parent account with child install-based items at the region level (not child accounts). Arizona will be added as a child account under UUG at go-live.

#### Email-to-Account Linking
Salena asked about linking emails to account records (similar to Salesforce's BCC-to-account feature). Melissa Alexander confirmed she used this in Salesforce for sales leads. The use case: knowledge continuity when a colleague is OOO or has left the team. [[Justice West]] acknowledged this is technically doable but is a future-phase item requiring solutioning; [[Aaron Banister (Me)|Aaron]] was asked to research it. Tom summarized the need as: "an easy way to transfer email conversations to an account record in ServiceNow."

#### UI Tips & Tricks
1. **Always Show Top Navigation** — Profile → Preferences → Display → "Always show top navigation." Prevents losing the nav bar when opening records in new tabs.
2. **Favorites & Sidebar Pinning** — Navigate to any view, click the star icon, then pin to sidebar. Create custom groups (demonstrated "Navigating Care" group) and drag favorites into them.
3. **Filtered Favorites** — Demonstrated filtering account team members by account owner = Heather Chase, then favoriting that view as "Heather's Accounts." Tom noted this could replace the Google Drive spreadsheet he currently uses to track team assignments.

#### Reporting & Dashboards
[[Aaron Banister (Me)|Aaron]] confirmed ServiceNow has a full reporting module. All attendees will be given access to build their own reports and dashboards. Tom plans to build a case dashboard for Melissa. [[Justice West]] described dashboards as "a concatenation of reports put together visually." Melissa confirmed she'll still want tabular reports she can export to Excel.

#### Next Steps
Tom outlined the go-live plan: load the Salesforce data snapshot into ServiceNow production targeting Monday, March 23. Suchaya Laddaphan noted the current environment is test — users should explore and try to break things through Friday. Tom and Suchaya will follow up on login access and check in 1-2x/week. Cases/support team onboarding is targeted for April 1.

### Action Items

**[[Aaron Banister (Me)|Aaron]]**
- [x] Research how to link/BCC emails to account records in ServiceNow (flagged by Salena, asked to note for research)  [priority:: high]  [completion:: 2026-03-23]
- [x] Provision CSM access to all stakeholders in production  [priority:: high]  [due:: 2026-03-20]  [completion:: 2026-03-23]
- [x] Load Salesforce data snapshot into ServiceNow production  [due:: 2026-03-20]  [completion:: 2026-03-23]