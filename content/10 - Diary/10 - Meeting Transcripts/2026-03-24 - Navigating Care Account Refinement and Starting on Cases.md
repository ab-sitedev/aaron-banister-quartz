## Meeting Summary

**Date:** 2026-03-24
**Attendees:** Aaron Banister (Me), Justice West, Tom McGovern, Suchaya Laddaphan

### Discussion

#### Accounts Punch List

Tom McGovern led a review of open accounts items with the goal of wrapping up in ~10 minutes before shifting to cases.

**Parent-child view:** Tom wanted to see a parent-child relationship view for accounts. [[Aaron Banister (Me)|Aaron]] agreed to send him details via Teams message.

**Hiding fields/tabs not used by the NC Team:** Tom asked whether fields like *legal entity name*, *industry*, *business structure*, and *date of incorporation* could be hidden for the Navigating Care team. [[Aaron Banister (Me)|Aaron]] confirmed it's feasible — a simple toggle for now since NC is the only team using the suite, with more dynamic configuration possible later. Tom will provide a list of fields to hide.

**Install base items — pulling account data:** Tom couldn't figure out how to surface account-level fields (e.g., a 4-character clinic code) in the install base items list view. [[Aaron Banister (Me)|Aaron]] explained this is available when configuring the default list view (not via personal list personalization), and offered to set it up. The team also discussed using reports or dashboards as an alternative for Debbie's monthly billing export workflow.

**Reports access:** Tom's group lacked reporting permissions. [[Justice West]] added report scheduler, report publisher, report user, and dashboard roles to their group. Tom had to log out and back in for the roles to take effect. [[Justice West]] then walked Tom through creating a report from the Install Base Items table, showing how to use the branch icon in "Choose Columns" to join to account-level fields (analogous to a SQL join).

**Group by Clinic ID error:** Tom encountered an unexpected error when trying to group a list view by Clinic ID. [[Aaron Banister (Me)|Aaron]] hadn't seen it before and will investigate.

**Sold products / licensed-but-not-live:** Tom and Suchaya will do cleanup of sold products (toggling active/non-active flags) together in the afternoon.

**URL slug / Custom Path mapping:** Suchaya flagged that the URL slug field was empty for 3 of the clinics she was validating. [[Aaron Banister (Me)|Aaron]] believes Salesforce's "Custom Path" was intended to map to the *name* field on the install base item, not the URL slug. Tom decided he and Suchaya will handle manual correction using the **list edit** trick [[Aaron Banister (Me)|Aaron]] demonstrated: double-clicking a cell in a list view to edit inline, allowing bulk copy-paste between columns without opening each record.

**Rollout plan:** Tom plans to roll out accounts tomorrow (2026-03-25) to account managers Selena, Heather, and Debbie, followed by CSMs later in the week. All users are in the same group and have identical permissions to Tom.

---

#### Cases

[[Aaron Banister (Me)|Aaron]] provided a status update on the cases setup:

- An incident was submitted Friday to the help desk to create the email inboxes needed for auto-case creation. Help desk resolved it Monday morning (today).
- Emails from those mailboxes are now hitting ServiceNow, and the inbound action flow is working — incoming emails trigger a flow that creates a case.
- Remaining work: assignment groups and dynamic routing (patient vs. clinic).

**Routing logic:** [[Justice West]] explained the current Salesforce approach — Zoom's phone tree sends a value to Salesforce to tag calls as patient or clinic. [[Aaron Banister (Me)|Aaron]] wants to see the actual email payload from Reid before configuring the routing in ServiceNow. [[Justice West]] suggested combining payload inspection with a check for existing contact/account records as a fallback.

**Error handling for routing:** Tom confirmed ~90–95% of volume is patient, so unroutable cases should default to the patient assignment group.

**Testing approach:** Tom proposed forwarding Zoom voicemails to both Salesforce (production) and the ServiceNow dev instance simultaneously, so the support team can process the same cases in both systems during a training window. [[Aaron Banister (Me)|Aaron]] noted that emails in sub-prod instances are disabled system-wide, so no customer-facing notifications will go out. Activity stream entries will still show if an email *would* have been sent in production.

**PHI in dev:** [[Justice West]] confirmed dev is okay for PHI (covered by BAA). Extra PHI encryption (added to the incident world) is a future enhancement, not MVP.

**Case layout:** Tom met with Melissa (yesterday) about case types and subtypes — she's in a good spot. [[Justice West]] scheduled a 9am meeting with [[Aaron Banister (Me)|Aaron]] for tomorrow (2026-03-25) to work through category/subcategory requirements and get the case form mostly built out.

---

### Action Items

- [ ] [[Aaron Banister (Me)|Aaron]] — Send Tom a Teams message with details on the parent-child account view
- [ ] Tom McGovern — Provide [[Aaron Banister (Me)|Aaron]] a list of fields/tabs to hide for the NC Team
- [ ] [[Aaron Banister (Me)|Aaron]] — Investigate the "group by Clinic ID" error in list views
- [ ] [[Aaron Banister (Me)|Aaron]] — Add account 4-character code column to the default install base item list view
- [ ] [[Justice West]] — Schedule a working session with Debbie to review and enhance her billing/export workflow
- [ ] Tom McGovern + Suchaya Laddaphan — Clean up sold products (active/non-active) this afternoon [due:: 2026-03-24]
- [ ] Tom McGovern + Suchaya Laddaphan — Manually correct URL slug / Custom Path data using list edit
- [ ] [[Aaron Banister (Me)|Aaron]] — Contact Reid to set up Zoom email forwarding to the ServiceNow dev instance for data flow testing
- [ ] [[Aaron Banister (Me)|Aaron]] — Configure case category/subcategory in ServiceNow based on requirements from Melissa and [[Justice West]]
- [ ] [[Aaron Banister (Me)|Aaron]] + [[Justice West]] — 9am working session tomorrow to finalize case form layout [due:: 2026-03-25]

---

## Transcript
WEBVTT

1
00:00:00.020 --> 00:00:01.740
aaronbanister: Yes.

2
00:00:02.530 --> 00:00:06.000
Justice West: Sorry, just heading to work. I was just a minute late.

3
00:00:06.000 --> 00:00:07.380
Tom McGovern: Yep.

4
00:00:07.380 --> 00:00:07.980
Justice West: I love it.

5
00:00:07.980 --> 00:00:10.059
Tom McGovern: Yeah, we are. Exactly.

6
00:00:10.350 --> 00:00:17.350
Tom McGovern: So I'll go through some punch list items for accounts for hopefully 5 minutes, no more than 10, and then we'll switch over to cases for the remainder period of the time.

7
00:00:17.940 --> 00:00:19.150
Justice West: Love it.

8
00:00:19.260 --> 00:00:21.879
Justice West: Aaron's your main man, he's been killing it, so…

9
00:00:21.880 --> 00:00:22.470
Tom McGovern: Yep.

10
00:00:23.590 --> 00:00:28.429
Tom McGovern: I got some punchless items here on the right, we'll just go through those. Suchaya, you can chime in, too, as well.

11
00:00:28.530 --> 00:00:35.229
Tom McGovern: So, Aaron, you don't have to show me, you can just throw that into, maybe just throw me into a Teams message.

12
00:00:35.920 --> 00:00:39.700
aaronbanister: Okay, is… Sachai, are you the host of this call?

13
00:00:40.510 --> 00:00:41.149
Suchaya Laddaphan: Yes, sir?

14
00:00:41.150 --> 00:00:49.519
aaronbanister: Or is it Tom? Okay. I don't know if you saw it, I put in a request to have this recorded, if you don't mind, just so that I can go back and look at the transcript for action items later.

15
00:00:49.520 --> 00:00:50.110
Suchaya Laddaphan: started.

16
00:00:50.400 --> 00:00:53.529
aaronbanister: Awesome, thank you. And I've got that one noted there, Tom.

17
00:00:53.680 --> 00:01:00.080
Tom McGovern: Okay? I'm interested on that one, because it was… I could see some in there, and then I was like, well, it'd be easier if I could see a parent-child, if that's possible.

18
00:01:00.210 --> 00:01:07.800
Tom McGovern: The next one is hide fields not used by NC Team, and the following one down here, hide tabs not being used by NC Team.

19
00:01:08.020 --> 00:01:16.520
Tom McGovern: not critical for us, but it is going to be coming up. I want to make sure all of us are on sync on how we think about that world. Is there a way to…

20
00:01:17.240 --> 00:01:18.670
Tom McGovern: customize the…

21
00:01:19.540 --> 00:01:20.220
aaronbanister: Yeah.

22
00:01:20.220 --> 00:01:28.450
Tom McGovern: screens for there, because many of those they don't use, and they're going to start asking me questions when China and I start meeting with tomorrow and start rolling it out from that world, so…

23
00:01:29.950 --> 00:01:36.429
aaronbanister: Do you already have a list of fields that you need hidden, and related lists that you need hidden?

24
00:01:37.040 --> 00:01:45.160
Tom McGovern: Yeah, like, certain ones, like over here, like legal entity name, industry, business structure, date of incorporation, I can get you a list on those, but certain ones like that.

25
00:01:45.760 --> 00:01:46.300
aaronbanister: Okay.

26
00:01:46.300 --> 00:01:50.599
Tom McGovern: If we could do that one. Okay, cool, I just want to make sure. And then down here, some of these we know we don't use.

27
00:01:52.090 --> 00:01:56.239
Tom McGovern: So is there a way to turn them off and turn them on when the business need arise?

28
00:01:57.560 --> 00:02:00.259
aaronbanister: There is. Yeah.

29
00:02:00.260 --> 00:02:03.390
Justice West: There is. Aaron, my question is, how much work is it, though?

30
00:02:03.390 --> 00:02:06.789
aaronbanister: The related lists can be,

31
00:02:07.430 --> 00:02:20.189
aaronbanister: I mean, they're all easy to show hide. Since Navigating Care is the only team using this whole suite at the moment, we can just do it across the board for cases and for accounts.

32
00:02:20.340 --> 00:02:28.289
aaronbanister: But then if the need arises later on to make that more dynamic, that's where it gets a little bit more complex. But for now, it would pretty much just be a toggle.

33
00:02:29.380 --> 00:02:35.590
Tom McGovern: I'll get you something there, and then as the business grows more and more, we can turn those fields and expose them back again. Great.

34
00:02:36.180 --> 00:02:37.010
Tom McGovern: Alright.

35
00:02:40.180 --> 00:02:42.270
Tom McGovern: On to install base items.

36
00:02:42.440 --> 00:02:43.430
Tom McGovern: Here…

37
00:02:44.580 --> 00:03:02.199
Tom McGovern: On the install base items? Is there a way… I can't figure out a way to pull in account information. For example, I want to pull in one of the, like, the code, one of the short codes, or something that's listed on the account field. I couldn't, for the life of me, figure out how to get that account information to be pulled in with install-based items.

38
00:03:02.730 --> 00:03:06.629
aaronbanister: Can you click the gear icon in the top right corner real quick, and just show me…

39
00:03:06.850 --> 00:03:15.679
aaronbanister: So, account… okay. That under-selected, how you have account there, if the feature was enabled, you'd be able to…

40
00:03:15.860 --> 00:03:22.100
aaronbanister: Expand that, and drill in to add columns from the account record.

41
00:03:22.810 --> 00:03:27.019
Justice West: Is it not? Tom, can you move a count back to the left real quick?

42
00:03:27.020 --> 00:03:27.570
Tom McGovern: Yeah.

43
00:03:27.640 --> 00:03:29.369
Justice West: This is probably gonna be silly.

44
00:03:30.510 --> 00:03:32.950
Justice West: Yeah, it's not… okay, never mind. Sorry, Aaron.

45
00:03:32.950 --> 00:03:41.239
aaronbanister: Yeah, it's always available whenever you're configuring the, like, the actual list view, not personalizing the list view.

46
00:03:41.470 --> 00:03:43.660
aaronbanister: So that's something that I can…

47
00:03:44.040 --> 00:03:48.369
aaronbanister: I can break out for you and just make it part of the default list view.

48
00:03:48.370 --> 00:03:48.760
Tom McGovern: Okay.

49
00:03:48.760 --> 00:03:53.020
aaronbanister: I don't know if it… yeah, I don't know if it's possible or not using the gear icon.

50
00:03:53.460 --> 00:03:58.629
aaronbanister: Okay. Or if it's a way that… something… I might be able to enable something that'll let you do it, I'm not sure.

51
00:03:58.880 --> 00:04:08.490
Tom McGovern: For example, one of the use cases is, if I gave Debbie this view, she would immediately say to me, can you put that four-character code column in this view?

52
00:04:08.650 --> 00:04:13.849
Tom McGovern: And I would say, well, I can't, because I can't pull it from the account level field just yet.

53
00:04:14.860 --> 00:04:15.680
aaronbanister: Is that what…

54
00:04:15.680 --> 00:04:20.799
Justice West: for working or viewing… sorry, Aaron, I was gonna say we could use a dashboard for that, but…

55
00:04:20.959 --> 00:04:24.039
aaronbanister: Yeah, we're on the same page, Justice, you're good. That's what I was gonna say, too.

56
00:04:24.870 --> 00:04:38.399
Tom McGovern: I'm fine either way, and I'm fine with… she's gonna ask me tomorrow when I meet with her, how can I have a report that I can work with that with as well? And I know that I can export list views, I figured that one out into, like, Excel or CSV or JSON.

57
00:04:38.680 --> 00:04:42.760
Tom McGovern: But I want to be able to marry install-based items with…

58
00:04:42.930 --> 00:04:50.270
Tom McGovern: this world, if it's more dynamic, if it's easier to work in a report structure or a dashboard structure, I'm not married either way.

59
00:04:51.020 --> 00:04:52.360
Tom McGovern: List views are more…

60
00:04:52.510 --> 00:05:00.709
Tom McGovern: List views are more operational in nature, in my mind, to go in and review them, and then take action upon changing a field or making an update to it.

61
00:05:00.710 --> 00:05:12.769
Justice West: That's… yes, that's the big difference between report. Report will give you a lot more easy functionality to add whatever fields from whatever table you want, very easily. It's just not always the best directly for, like.

62
00:05:13.160 --> 00:05:20.310
Justice West: you know, as a list view, because I could use… from a list view, you could just go in, like, edit the field, and, like, update the value, right? Like, that kind of stuff.

63
00:05:20.470 --> 00:05:30.019
Justice West: So it just depends on what the use case is. Is that more just for her to get a glance at it, or would it be more for her to, like, work out of and, like, make edits and changes?

64
00:05:30.020 --> 00:05:41.870
Tom McGovern: She won't make edits, what she'll do is the other team members make edits to these counts on a monthly basis, and then she'll do an export and marry it up with the accounting system needs, and then generate invoices applicably.

65
00:05:42.060 --> 00:05:49.720
Tom McGovern: So she will take an export… she will take an export and memorialize it as a source of truth for her monthly billing.

66
00:05:50.960 --> 00:05:56.309
Justice West: Yeah, that's good. It actually has me thinking. I probably just need to work with Debbie and her workflow at some point for just…

67
00:05:56.480 --> 00:06:04.139
Justice West: 30 minutes to an hour, and… because we could even probably enhance some of that really easily on, like, just a little work session. Like.

68
00:06:04.440 --> 00:06:08.520
Justice West: You know, I could even… you could even generate a report of, like, what… what has changed.

69
00:06:08.960 --> 00:06:25.799
Justice West: Or what, like, that kind of stuff. Yeah. There's all kinds of things we do. But in the meantime, I think using reports and stuff is the way to go. I… not that Aaron… Aaron, you can definitely do it if you have the time. If not, I can probably make some time and…

70
00:06:26.590 --> 00:06:28.119
Justice West: And work on that.

71
00:06:28.120 --> 00:06:46.509
Tom McGovern: That was my next item down here, thinking you guys were going to say that, which is, can you just provide the team access to build reports? Or at least provide me ones and allow them to read them, because tomorrow she'll say, hey, how do I… Debbie will say when she meets… we meet with her and the account managers to start rolling it out, is, okay, Tom, where do I see my monthly report that I'm going to need a week from tomorrow?

72
00:06:46.680 --> 00:06:54.879
Tom McGovern: which is the first, is she'll do an export out of ServiceNow, and then run it through a process. And I want to build it, try to build it to her before I meet with her tomorrow morning.

73
00:06:55.180 --> 00:07:05.339
Justice West: the best way to do that, and… because, one, we can just give you access. In fact, you probably have access right now, you just don't realize it, but second would be…

74
00:07:05.570 --> 00:07:13.379
Justice West: The way I typically like to educate on reports is, like, do a 30-minute work session, and, like, we… you literally have a report in mind you want to build.

75
00:07:13.510 --> 00:07:17.210
Justice West: And I walk you through building it. Like, the doing is learning, kind of.

76
00:07:17.380 --> 00:07:24.090
Justice West: thing, I've found the most success with. I'm happy to do that, but if you're like, I just need to whip something up today, we can't make calendars work.

77
00:07:24.280 --> 00:07:27.209
Justice West: Go click on your…

78
00:07:28.350 --> 00:07:35.899
Justice West: Let's see, I'm running around. And click all, and click, view, or type… or just type in the future, view slash run.

79
00:07:37.970 --> 00:07:38.940
Justice West: Give me the space.

80
00:07:38.940 --> 00:07:40.220
aaronbanister: After the slash.

81
00:07:40.220 --> 00:07:41.100
Justice West: after that.

82
00:07:41.100 --> 00:07:42.090
aaronbanister: Before the slash.

83
00:07:44.060 --> 00:07:49.409
Justice West: Yeah, go back, sorry, it was right there. Yeah, click that, and you'll want to favorite that guy, too.

84
00:07:50.870 --> 00:07:53.140
Justice West: Beautiful.

85
00:07:54.020 --> 00:07:56.410
Justice West: So, yeah, click him again.

86
00:07:58.140 --> 00:08:02.110
Justice West: And so… You'll wanna wait.

87
00:08:02.500 --> 00:08:04.849
Justice West: Aaron, this is a weird view.

88
00:08:04.850 --> 00:08:07.889
aaronbanister: Yeah, I don't know if he has access to create.

89
00:08:07.890 --> 00:08:09.580
Justice West: No! Okay, I'll do that.

90
00:08:09.580 --> 00:08:11.420
aaronbanister: Well, I mean, it's acting like he…

91
00:08:13.010 --> 00:08:16.610
aaronbanister: Oh, no, it's just because he hasn't created any. We're looking at my reports.

92
00:08:16.610 --> 00:08:16.970
Tom McGovern: than I'm.

93
00:08:16.970 --> 00:08:22.440
Justice West: Oh, yeah, go to All or something. Maybe there'll be… I thought there would be, like, a new button in the right corner.

94
00:08:26.580 --> 00:08:27.620
Justice West: Weird.

95
00:08:30.030 --> 00:08:33.730
Justice West: Did you get their group set up, Aaron?

96
00:08:33.750 --> 00:08:40.820
aaronbanister: Yeah, they, I mean, they only have access to the CSM stuff, no explicit access was given for reporting.

97
00:08:41.370 --> 00:08:45.089
Justice West: Yeah, let me just add a role for report.

98
00:08:45.910 --> 00:08:52.269
Justice West: Report scheduler, report publisher, report user…

99
00:08:53.060 --> 00:08:56.130
Justice West: And then we're gonna also throw dashboard.

100
00:08:56.130 --> 00:09:03.230
Tom McGovern: Alright, while he does that, Aaron, just an FYI, my next time on my list, if I try to, like, group by clinic ID,

101
00:09:03.690 --> 00:09:11.039
Tom McGovern: So I have clinic ID here, and it's like going, like, okay, like, Texas, you know we have four of those. I go, like, oh, I'm gonna try to group these up and see these totals.

102
00:09:11.920 --> 00:09:17.170
Tom McGovern: So I do group by, and I do clinic ID, and I get that error.

103
00:09:18.810 --> 00:09:21.050
Tom McGovern: Which I noted here my next time on my list.

104
00:09:23.720 --> 00:09:24.860
aaronbanister: Oh, that's interesting.

105
00:09:28.400 --> 00:09:29.770
aaronbanister: Let me take a screenshot of that.

106
00:09:29.970 --> 00:09:34.549
Tom McGovern: And it's also out here, we've added this punch list out on the SharePoint site, and you'll see I've copied it.

107
00:09:34.550 --> 00:09:35.370
aaronbanister: Oh, nice.

108
00:09:35.370 --> 00:09:46.629
Tom McGovern: So I'm just going down this list. So you can bury it up with the transcript from this Zoom call, but also, pretty much, I'm just going literally down the list to keep us in sync on what I'm talking about.

109
00:09:46.630 --> 00:09:47.400
aaronbanister: Love it.

110
00:09:47.730 --> 00:09:49.170
aaronbanister: I'll refer to that then.

111
00:09:51.460 --> 00:09:53.409
Tom McGovern: Whether it's product validation.

112
00:09:53.670 --> 00:09:58.950
Tom McGovern: what is it? It's such a product validation, accounts list, yeah, tracking list. Okay, go ahead.

113
00:10:00.520 --> 00:10:03.549
aaronbanister: I gotta be honest, I haven't… I've never seen that error message before, so…

114
00:10:03.550 --> 00:10:03.910
Tom McGovern: Great.

115
00:10:03.910 --> 00:10:05.870
aaronbanister: I'll look in… I'll look into that research.

116
00:10:05.870 --> 00:10:09.680
Tom McGovern: But I could get around it for today, but that's what I was trying to reconcile coming back.

117
00:10:10.050 --> 00:10:18.690
Tom McGovern: I'm trying to reconcile all those provider counts, marry it up with account information, and then create a report, and then I thought, oh, I'll just do grouping by clinic ID, maybe that'll help me out.

118
00:10:18.690 --> 00:10:22.499
aaronbanister: Will it let you group by something else? Like, group by account, maybe?

119
00:10:22.500 --> 00:10:23.389
Tom McGovern: Let me see.

120
00:10:24.750 --> 00:10:26.659
aaronbanister: Just, like, purely out of…

121
00:10:27.090 --> 00:10:31.560
aaronbanister: Is it an access thing, or is it just, like, a weird thing with that? It's a weird thing with that field, huh?

122
00:10:32.310 --> 00:10:33.070
Tom McGovern: like it.

123
00:10:33.260 --> 00:10:33.900
aaronbanister: Okay.

124
00:10:37.110 --> 00:10:38.299
aaronbanister: Yeah, I'll check it out.

125
00:10:40.420 --> 00:10:44.809
Justice West: Alright, Tom, go back to that report thing real quick when you get a chance.

126
00:10:46.670 --> 00:10:51.959
Justice West: You might need… might make you log out and back in. Refresh that one more time? Yeah.

127
00:10:53.400 --> 00:10:54.260
Justice West: It's,

128
00:10:54.800 --> 00:11:00.049
Justice West: Gross. Alright, yeah, you'll have to… unless I didn't save… yeah, it says I saved this group, so…

129
00:11:00.550 --> 00:11:05.260
aaronbanister: Yeah, it pretty much makes you log out and back in for any… Permissions update.

130
00:11:09.960 --> 00:11:18.679
aaronbanister: While he's doing that, Justice, fun fact, as admins, if you just impersonate somebody and then end impersonation, that'll update your roles too, if you have the impersonator role.

131
00:11:18.680 --> 00:11:21.930
Justice West: Yeah, that's right, you told me that a long time ago, I never use it.

132
00:11:21.930 --> 00:11:23.250
aaronbanister: There's the create button.

133
00:11:23.490 --> 00:11:25.290
Tom McGovern: Right here. That's what you guys are looking for?

134
00:11:26.290 --> 00:11:26.860
aaronbanister: Yeah.

135
00:11:27.380 --> 00:11:34.550
Justice West: So, really, the main… if you click it, I'll do the two-second version, that you can play with. Main first thing is table.

136
00:11:34.740 --> 00:11:47.299
Justice West: Now, some things you're going to be looking for are going to be in multiple different tables, so just pick the table, typically, that, like, is your… the majority of your fields are going to be from. So, you'll probably want it to be…

137
00:11:48.320 --> 00:11:51.639
Justice West: What do we think? The install base items?

138
00:11:53.000 --> 00:11:53.970
Justice West: You can start…

139
00:11:53.970 --> 00:11:56.350
aaronbanister: There, and see what… What walls you hit.

140
00:11:56.860 --> 00:12:02.000
Justice West: Yeah, so give it just a name of some sort, you'll have to do something in that field to get to the next.

141
00:12:02.100 --> 00:12:07.889
Justice West: Stat… Alright, so hit next, and then… you can always rename it, too.

142
00:12:08.070 --> 00:12:12.989
Justice West: scroll down, there's all kinds of… on the left side, on the types, I think it'll default into the list.

143
00:12:13.250 --> 00:12:24.339
Justice West: Is that what that is? Yeah. Yeah. So that's probably where we're going to start anyway. And then go to Configure, and this will show you the one piece, because you know how to do filters and stuff. Choose columns, yes.

144
00:12:24.650 --> 00:12:26.230
Justice West: Now do you say…

145
00:12:26.230 --> 00:12:27.189
aaronbanister: That's what I was talking about.

146
00:12:27.190 --> 00:12:32.079
Justice West: Like, green at the top, so click that account with, like, the little plus next to it.

147
00:12:34.090 --> 00:12:40.349
Justice West: Actually click the little thing in the middle that looks like the little branch, looking… yeah, that guy.

148
00:12:40.460 --> 00:12:54.520
Justice West: So now you're, like, in the account fields. So it's like you're doing a join in a SQL table, so, like, you just pull… so then you can… you can even drill down further, and, like, further and further and further, but I think everything you need should be, like, in that…

149
00:12:54.970 --> 00:12:56.849
Justice West: Account table, for the most part.

150
00:12:57.100 --> 00:12:57.780
Tom McGovern: Got it.

151
00:12:59.100 --> 00:13:02.889
Justice West: So, yeah, so that would be it. Then you just do your filters, and…

152
00:13:03.290 --> 00:13:13.480
Justice West: you're more or less done. There's a couple little things, like just making sure it's available for everybody and not private, stuff like that, but that's really the long and short, if you have a technical background.

153
00:13:13.830 --> 00:13:15.190
Tom McGovern: Yeah, I'm good there.

154
00:13:16.010 --> 00:13:27.280
Tom McGovern: How'd you get to the tables to pick? If I want to pick a second table, let's say I want to marry install base with accounts, or did it already have that join in the green because it already knew there was a relationship?

155
00:13:27.390 --> 00:13:27.990
Tom McGovern: Yeah.

156
00:13:27.990 --> 00:13:36.120
Justice West: when you go to that choose columns, and when you just add that field in, it will do that join on the back end for you. That's why I said, it's like, once you

157
00:13:37.100 --> 00:13:40.559
Justice West: Yeah, so, like, if you scroll up, and you just go to, like, the accounts field.

158
00:13:41.050 --> 00:13:48.810
Tom McGovern: And the reason why you guys asked me why… which table you can use the most, start with that table, like I did InstallBase.

159
00:13:49.060 --> 00:13:51.780
Tom McGovern: Because that's going to give you all the joins you want. Okay.

160
00:13:51.780 --> 00:14:06.800
Justice West: Yep, yep, yep. And I mean, it just depends on what you want, right? Like, it may be the account table may be the best place to start, depending on what you're looking for, but you kind of… I just typically… what I do is use my best guess, going in, and then I'll revise if I need to switch the table.

161
00:14:07.370 --> 00:14:08.510
Tom McGovern: Got it. Okay.

162
00:14:09.430 --> 00:14:10.240
Tom McGovern: Thank you.

163
00:14:10.490 --> 00:14:11.050
Justice West: Yep.

164
00:14:11.050 --> 00:14:22.409
Tom McGovern: Group of licensed products, but not live. So, Chaya, we'll go through the sold products. You and I have to do some cleanup work there, and there's, like, an active or non-active, and we'll just click… you and I will go through that, maybe this afternoon.

165
00:14:22.410 --> 00:14:23.060
Suchaya Laddaphan: Yeah.

166
00:14:23.060 --> 00:14:24.180
Tom McGovern: Put those on and off.

167
00:14:24.180 --> 00:14:34.130
Suchaya Laddaphan: I was taking more of, deeper data validation approach, like screen by screen and feel by feel, so… and then the second one that I had there is that…

168
00:14:34.520 --> 00:14:39.849
Suchaya Laddaphan: Aaron, just want to confirm that URL slot's supposed to be a custom path?

169
00:14:40.680 --> 00:14:41.670
Suchaya Laddaphan: Right?

170
00:14:42.830 --> 00:14:44.180
aaronbanister: Neither.

171
00:14:44.450 --> 00:14:46.329
aaronbanister: Try to recall that one.

172
00:14:46.580 --> 00:14:47.859
aaronbanister: Let me pull one up.

173
00:14:48.040 --> 00:14:48.970
Justice West: What is that?

174
00:14:49.980 --> 00:14:50.679
aaronbanister: So they…

175
00:14:50.680 --> 00:14:52.310
Suchaya Laddaphan: You… yeah, go ahead, Aaron.

176
00:14:52.800 --> 00:14:54.840
aaronbanister: Oh, you'll probably know better than me, I'll let you talk.

177
00:14:54.840 --> 00:15:02.930
Suchaya Laddaphan: So, just as this field from Salesforce, we call it Custom Path, but I think we didn't…

178
00:15:03.520 --> 00:15:11.460
Suchaya Laddaphan: quite confirm if that custom path translated to a URL slug in ServiceNow.

179
00:15:11.800 --> 00:15:26.060
Suchaya Laddaphan: my original, understanding was that it is, but there were no data in the URL slug field for, so far, 3 of the clinic that I'm doing data validation on.

180
00:15:26.440 --> 00:15:27.140
Justice West: Gotcha.

181
00:15:27.310 --> 00:15:31.280
aaronbanister: Yeah, and that… that is where that was supposed to map, Sachaya, for… just from what I'm…

182
00:15:31.490 --> 00:15:41.400
aaronbanister: Okay. I mean, it just looks like that's what it was supposed to do. I don't know if we maybe talked about it and it was up in the air or not, but if that's where it should be, then I can do another transform and get them in there.

183
00:15:42.310 --> 00:15:46.729
Tom McGovern: Go ahead and stay on cases. Su Chai and I will handle it.

184
00:15:47.270 --> 00:15:54.069
aaronbanister: I, I, actually, I think the custom path may have mapped to the name field on the install base item.

185
00:15:54.070 --> 00:15:57.999
Suchaya Laddaphan: Yeah, and I was gonna ask, I have noticed the past 3 accounts that I've

186
00:15:58.160 --> 00:16:06.460
Suchaya Laddaphan: was doing data validation on under that install base item, and then I'm seeing that name is matching the custom path.

187
00:16:06.930 --> 00:16:09.409
Suchaya Laddaphan: Okay. So is that the intent?

188
00:16:10.910 --> 00:16:11.460
Tom McGovern: But it's a.

189
00:16:11.890 --> 00:16:12.590
Tom McGovern: style.

190
00:16:13.240 --> 00:16:20.959
aaronbanister: I mean, yeah, I mean, if you guys want to take it, you can. It's not too hard for me to build, like, a quick, small transform map.

191
00:16:20.960 --> 00:16:27.220
Suchaya Laddaphan: We can circle… yeah, we can circle back on this. I just want to flag what I've seen so far. Okay. Other than that, yeah.

192
00:16:27.340 --> 00:16:36.220
Tom McGovern: Aaron, let's Sachai and I look at it. If it's something that's going to take us 5-7 minutes, it's just to bust through the accounts to do it, like I did with the one oncology ones that I did this morning.

193
00:16:36.430 --> 00:16:39.760
Tom McGovern: I'm just gonna do it because I'd rather you focus on the cases side of the world.

194
00:16:39.760 --> 00:16:40.120
aaronbanister: Okay.

195
00:16:40.120 --> 00:16:41.120
Tom McGovern: on that world, so…

196
00:16:41.120 --> 00:16:47.530
aaronbanister: And if you guys are gonna do it, let me… before you start, let me show you a quick way that might…

197
00:16:47.530 --> 00:16:51.719
Justice West: I just know what you're doing. Go ahead.

198
00:16:51.720 --> 00:16:52.730
aaronbanister: List editing.

199
00:16:53.010 --> 00:16:53.710
Justice West: Yeah.

200
00:16:53.860 --> 00:17:05.410
aaronbanister: Let me know, you guys, if… because there are specific ACLs that restrict the ability to do this, and I haven't tested to see if you guys can.

201
00:17:05.630 --> 00:17:08.680
aaronbanister: But do give it a shot.

202
00:17:09.190 --> 00:17:20.900
aaronbanister: I'm in the install base items. I'm going to make sure that name is visible, and URL slug is visible. I'll put them right next to each other, just for simplicity.

203
00:17:23.990 --> 00:17:31.719
aaronbanister: what you can do is… I can just, without, you know, drilling into the record and waiting for the form to load each time.

204
00:17:31.720 --> 00:17:32.470
Tom McGovern: Yeah.

205
00:17:32.470 --> 00:17:39.629
aaronbanister: Instead, I can just double-click the empty space around the data in one of these cells, and then I can copy this.

206
00:17:39.630 --> 00:17:40.130
Suchaya Laddaphan: Aw.

207
00:17:40.130 --> 00:17:45.119
aaronbanister: And then do the same thing in URL slug and paste it there. And just do that over and over.

208
00:17:45.120 --> 00:17:45.750
Tom McGovern: Cool.

209
00:17:46.830 --> 00:17:48.969
Suchaya Laddaphan: Easy peasy, okay, cool. Thank you.

210
00:17:49.520 --> 00:17:55.469
Tom McGovern: I saw some setting there that said list edit. Is that… is that that checkbox I saw somewhere?

211
00:17:55.600 --> 00:17:58.910
Tom McGovern: It said list edit in one of the preferences somewhere.

212
00:17:59.780 --> 00:18:00.799
Tom McGovern: That's what's hot.

213
00:18:00.810 --> 00:18:03.359
aaronbanister: Yeah, this is what that is, whenever you…

214
00:18:04.300 --> 00:18:15.049
Tom McGovern: And it was checked. I said, oh, I'll just check that one to make sure, make sure it stays checked, or whatever it was. I go, I don't know how to use it, so I went into every account this morning just to change it. The old-fashioned way, but I'm on with it.

215
00:18:15.270 --> 00:18:17.040
Tom McGovern: Cool. Shin and I know what to do. Cool.

216
00:18:18.030 --> 00:18:23.810
Tom McGovern: Alright, that's all I have for accounts. Otherwise, we're looking good. We're looking to roll it out to…

217
00:18:24.070 --> 00:18:28.099
Tom McGovern: the account manager, Selena and Heather, and Debbie, tomorrow.

218
00:18:28.420 --> 00:18:36.200
Tom McGovern: And then we'll do a couple CSMs later in the week, it all looks good, customer success managers, and then we'll be ready then

219
00:18:36.530 --> 00:18:39.499
Tom McGovern: Assuming everything's good there, we'll probably get some fit and finish feedback.

220
00:18:40.130 --> 00:18:44.809
Tom McGovern: We'll be focusing on bringing on the cases and the support team as soon as we're ready to do that.

221
00:18:46.000 --> 00:18:48.780
Tom McGovern: That's our plan right now, so…

222
00:18:49.070 --> 00:19:07.050
Tom McGovern: I'll build some reports for them, just to make sure that they have access to production, because we're going to take them and have them log in tomorrow, set their preferences, show them shortcuts, show them like I showed you how all my lists I created on the left-hand side was one, because I wanted them, and two, because I want to teach myself how to do it, and how to modify, and the preferences.

223
00:19:07.050 --> 00:19:16.700
Tom McGovern: changing columns, or if I change the filtering on a particular list, and how to reorder the list, and change the icons, and change the colors, all that stuff. So I feel pretty good about that on the lists.

224
00:19:17.150 --> 00:19:22.009
Tom McGovern: I'll… if I'm ready, I'll teach Debbie some of the reports, assuming she has access to reports, Erin.

225
00:19:22.200 --> 00:19:27.369
Tom McGovern: But really, those people are the ones we're going to be focusing on next couple days, is those 5 or 6 people.

226
00:19:27.600 --> 00:19:35.069
Tom McGovern: And get them all launched on using ServiceNow and making their updates before month end, so Debbie can do that export on the 1st, out of ServiceNow.

227
00:19:35.270 --> 00:19:37.980
Tom McGovern: And get all the counts that she needs to do for billing.

228
00:19:38.700 --> 00:19:44.729
Tom McGovern: Realizing, Justice, that there's some better ways for her to operate, and you're gonna find her, whether before or after the month-end stuff.

229
00:19:45.070 --> 00:19:45.660
Justice West: Yep.

230
00:19:45.660 --> 00:19:48.970
Tom McGovern: Yep. All right. Aaron, question?

231
00:19:49.190 --> 00:19:53.549
Tom McGovern: Don't embrace, are they all good, then, to log into production for tomorrow?

232
00:19:54.560 --> 00:19:59.789
aaronbanister: Yes, you guys are all in the same group, so any roles you have, they have.

233
00:19:59.790 --> 00:20:01.830
Tom McGovern: they can see. So anything I can do, they can do.

234
00:20:02.530 --> 00:20:03.580
aaronbanister: Yep. Perfect.

235
00:20:03.630 --> 00:20:05.510
Tom McGovern: I like it. I'm good.

236
00:20:05.820 --> 00:20:07.900
Tom McGovern: So, Chai, anything else on accounts?

237
00:20:09.480 --> 00:20:13.259
Suchaya Laddaphan: Not at this time, I'm not through with data validation, so…

238
00:20:13.260 --> 00:20:14.289
Tom McGovern: That's for you and I.

239
00:20:15.220 --> 00:20:26.880
Tom McGovern: And so, okay, so it's… we got some of our action items. If we want to change some field names, or change… we'll ask those, or hide some tabs, or hide some fields, we'll get back to Aaron after you and I go through the validation some more. Cool. All right.

240
00:20:27.960 --> 00:20:29.859
Tom McGovern: I think we're looking good for the Morrisichaya.

241
00:20:30.920 --> 00:20:32.540
Justice West: Still exciting.

242
00:20:32.540 --> 00:20:33.870
Tom McGovern: Alright, cases.

243
00:20:34.290 --> 00:20:42.720
Justice West: Aaron, what's the latest status there? I should have found time with you to touch base internally, but I've yet to do so. That's on me.

244
00:20:43.440 --> 00:20:54.670
aaronbanister: You're good. I had… I had the incident that I… that I requested from our help desk to create the emails necessary to get cases auto-creating.

245
00:20:54.960 --> 00:20:59.639
aaronbanister: to their credit, I submitted that late on Friday, so they weren't able to get to it. Super…

246
00:20:59.860 --> 00:21:03.029
aaronbanister: early on Monday, they got, they got to it early this morning.

247
00:21:03.320 --> 00:21:11.619
aaronbanister: So I tested that. Emails are hitting ServiceNow from that mailbox, and my test…

248
00:21:12.400 --> 00:21:19.459
aaronbanister: inbound action flow is working. So when an email comes in from one of those, right now, just one of those two emails.

249
00:21:19.670 --> 00:21:22.020
aaronbanister: It triggers the flow and creates a case.

250
00:21:22.340 --> 00:21:29.289
aaronbanister: So it still needs some refinement. We'll probably need to talk about assignment groups and dynamic routing, if that's a thing, otherwise I can just have

251
00:21:29.770 --> 00:21:31.190
aaronbanister: to one assignment? Okay.

252
00:21:32.290 --> 00:21:39.800
Justice West: It'll just be the field for clinic or patient. So, Tom, the operational question I need from you…

253
00:21:40.240 --> 00:21:42.850
Justice West: Or just talk through real quick here.

254
00:21:42.990 --> 00:21:49.290
Justice West: is… what trigger do we use to do that routing? So, obviously, we'll have the trigger

255
00:21:49.460 --> 00:21:59.589
Justice West: on the ServiceNow side, if we already have that contact. But if we don't, my understanding is, Aaron, I think the way they do it today is when Zoom

256
00:22:00.250 --> 00:22:02.069
Justice West: kind of processes.

257
00:22:02.170 --> 00:22:06.680
Justice West: And they're doing that You know, phone tree type situation.

258
00:22:06.830 --> 00:22:11.090
Justice West: it sends Salesforce a particular value.

259
00:22:11.720 --> 00:22:17.150
Justice West: That then they use to tag, like, can tag as a patient or a clinic.

260
00:22:17.300 --> 00:22:18.220
Justice West: user.

261
00:22:18.410 --> 00:22:27.700
aaronbanister: Yeah, and I want to start seeing what that data looks like. Now that we've got the email address set up, I can send that over to Reid and have some data flow in to the dev instance that way.

262
00:22:28.110 --> 00:22:32.069
Justice West: Yeah, so, Tom, I guess my one error handling question would be…

263
00:22:32.220 --> 00:22:37.969
Justice West: Hopefully, every single ticket we have is routed to one of the patient group or the clinic group.

264
00:22:38.550 --> 00:22:46.640
Justice West: If we have, like, an error or something, you know, the system happens, bug, whatever, and doesn't know where to put somebody, what group should we put it in?

265
00:22:50.240 --> 00:22:52.909
Tom McGovern: 90% of the volume is patient.

266
00:22:53.100 --> 00:22:59.899
Tom McGovern: 95%, so I would say we're putting in the group that has the highest amount of volume, because that makes the most sense that.

267
00:22:59.900 --> 00:23:00.520
Justice West: That makes sense.

268
00:23:00.520 --> 00:23:01.990
Tom McGovern: Probability that's gonna be there.

269
00:23:02.470 --> 00:23:09.659
Justice West: Yep, awesome. So, Aaron, we'll probably just need to get that payload from Reid and team, and…

270
00:23:09.940 --> 00:23:18.410
Justice West: kind of see what values we get. I don't think the team cares how you configure it, as long as if it's a patient, it goes to patient. If it's a clinic, it goes to clinic.

271
00:23:18.870 --> 00:23:25.770
Justice West: We can use some combination of payload, and then maybe have a second part of the flow that checks if it's an existing account record.

272
00:23:26.120 --> 00:23:31.869
Justice West: Or, contact slash user record, just in case we already have that information and it gets confused.

273
00:23:32.000 --> 00:23:34.280
Justice West: I trust your judgment on how to do that, though.

274
00:23:35.220 --> 00:23:35.800
aaronbanister: Okay.

275
00:23:38.690 --> 00:23:52.520
Tom McGovern: I don't know if the payload's different, if it's coming in from a Zoom voicemail versus a email to clinic support or patient support navigatingcare.com, or that online form. The payloads might be different based upon the source.

276
00:23:52.920 --> 00:23:55.139
Justice West: Yeah, I think it probably will be, yeah.

277
00:23:55.140 --> 00:23:55.770
Tom McGovern: Okay.

278
00:23:56.230 --> 00:24:14.880
Tom McGovern: My thinking here is, Aaron, you can obviously start with Zoom, or wherever you want to start with that one, have it start flowing in in parallel, just have them add another forwarding, so whenever a new, let's say, voicemail for Zoom comes in, we can have it forward to Salesforce in production today, and have it also forward to your dev environment, or test.

279
00:24:14.980 --> 00:24:25.809
Tom McGovern: And you can leave it on for an hour, you can just have it just keep filling up. And my thinking here is, when we're ready, I'm gonna tell the support team and become trained, is, okay.

280
00:24:25.920 --> 00:24:37.869
Tom McGovern: we're gonna run it for an hour or two and test, or dev. You guys log in there after you guys are working in Salesforce, and find those same cases and process them in ServiceNow, as you just did in Salesforce.

281
00:24:38.150 --> 00:24:50.230
Tom McGovern: So that they could have the exact same case that they handled in Salesforce showing up in ServiceNow, and we don't have to run it 24 hours a day, we could run it for, like, 4 hours, or whatever, and say, okay, could you handle that Zoom voicemail call?

282
00:24:50.580 --> 00:25:02.420
Tom McGovern: in an efficient way in ServiceNow, and understand what you have to do if we're actually in production. And give them that rehearsal over and over again, until they're comfortable, and we validate that the records are coming across.

283
00:25:02.760 --> 00:25:05.300
Tom McGovern: from… Voicemail?

284
00:25:05.420 --> 00:25:06.570
Tom McGovern: forms.

285
00:25:06.760 --> 00:25:12.860
Tom McGovern: And emails, and allow them to do some data validation, as well as some training at the same time.

286
00:25:13.390 --> 00:25:15.169
Tom McGovern: Did that make sense?

287
00:25:16.420 --> 00:25:18.010
aaronbanister: Yeah, yeah, I think so.

288
00:25:19.530 --> 00:25:21.589
Tom McGovern: So you can turn it on with Reed.

289
00:25:21.750 --> 00:25:24.040
Tom McGovern: And you can run it 24-7.

290
00:25:24.310 --> 00:25:36.099
Tom McGovern: Realizing it's PHI information in there, possibly, because people will just post them in emails that we go, like, okay, that was nice of you guys to do that. Patient. We really didn't want to get your whole family history in an email, but we got it.

291
00:25:36.130 --> 00:25:46.150
Tom McGovern: So, just realizing that will come through, there's a good chance. And, you can run it 24-7, or you can run it, you know, for 3 or 4 hours, and have Reed turn it back off again, just to get some…

292
00:25:46.310 --> 00:25:52.189
Tom McGovern: Volume of records during the middle of the day, and we can analyze that and just do some iterations on that.

293
00:25:52.650 --> 00:26:01.920
aaronbanister: Yeah, and we can even, turn them off on the ServiceNow side, where it'll just reject whatever emails come in from the forwarding, that way we don't have to ping read too much.

294
00:26:01.920 --> 00:26:07.389
Tom McGovern: it, I like that, to just drop some, and then we can just turn it back on at our own desire. Cool.

295
00:26:07.670 --> 00:26:14.560
aaronbanister: Yeah, and Justice, are we… we're good to have PHI potentially coming into the dev instance, just at a system level?

296
00:26:15.380 --> 00:26:20.430
Justice West: We are. I would… a future enhancement would be to…

297
00:26:20.810 --> 00:26:24.129
Justice West: incorporate our PHI enhancements to it.

298
00:26:24.320 --> 00:26:32.169
Justice West: I wouldn't say that's a part of MVP, because we're still protected by the BAA, but that was just an act. So, Tom, it was an extra thing we did,

299
00:26:33.300 --> 00:26:43.530
Justice West: in our incident world, which just made an extra level of encryption for PHI. It wasn't like a, you have to do this for HITRUST or for BAA, but it was just, like, a nice-to-have.

300
00:26:43.580 --> 00:26:54.599
Justice West: So eventually, we want to add that to you guys, too. Somehow, it'll have to be a little bit of a different approach, since the whole idea of this is we have patients, it's not like an exception, it's more the rule.

301
00:26:54.790 --> 00:26:58.539
Justice West: So just something that we probably need to account for in the future.

302
00:26:58.840 --> 00:26:59.440
Tom McGovern: Okay.

303
00:27:00.180 --> 00:27:11.629
Tom McGovern: What do you think… and we know we met, so I… Justice and I met with Melissa yesterday and talked to her about the types and subtypes, and we feel like she's in a good spot with those, although she said she was going to talk about it internally.

304
00:27:11.810 --> 00:27:16.409
Tom McGovern: When do you guys feel that the actual case

305
00:27:16.540 --> 00:27:25.329
Tom McGovern: layout in ServiceNow. I know we were talking about intake a minute ago, but the case layout is in a position where I can take some screenshots from it and dev or test.

306
00:27:25.430 --> 00:27:28.530
Tom McGovern: And be able to socialize it more with the team, to give them just starting.

307
00:27:28.530 --> 00:27:29.100
Justice West: Aaron?

308
00:27:29.170 --> 00:27:30.460
Tom McGovern: With a look and feel.

309
00:27:30.870 --> 00:27:34.850
Justice West: Well, do you think… I think Melissa was scheduled, so Aaron, I think we can use that.

310
00:27:35.150 --> 00:27:38.920
Justice West: those requirements I had for subcategory, category, and stuff.

311
00:27:39.600 --> 00:27:42.600
Justice West: That's easy to plug in, right?

312
00:27:43.850 --> 00:27:44.909
aaronbanister: Yeah, it's not too bad

313
00:27:45.490 --> 00:27:51.889
aaronbanister: Okay. Between that, and then we just need to get requirements on, like, what fields we want to show up on the form,

314
00:27:52.160 --> 00:27:52.830
aaronbanister: And birds.

315
00:27:52.830 --> 00:28:01.309
Justice West: have the rest of those, so Aaron, what we should do is, if you can work on the category, subcategory, or just the little things you know, I'm gonna find time with you

316
00:28:01.800 --> 00:28:08.160
Justice West: Tomorrow… And we can just knock that out, or at least… Get it mostly done.

317
00:28:08.780 --> 00:28:09.450
aaronbanister: Okay.

318
00:28:16.660 --> 00:28:19.620
Justice West: Working on getting that scheduled.

319
00:28:19.920 --> 00:28:20.510
Tom McGovern: These are all…

320
00:28:20.530 --> 00:28:21.180
Justice West: Yeah.

321
00:28:21.180 --> 00:28:28.879
Tom McGovern: These are all patients because they're highlighted in purple. These are all the two clinic ones, they're highlighted in green, and then we got the all for technical and defects.

322
00:28:30.190 --> 00:28:34.159
Justice West: I just put a call on your calendar, Aaron, for tomorrow morning at 9am.

323
00:28:35.320 --> 00:28:35.850
aaronbanister: F.

324
00:28:38.250 --> 00:28:41.299
Justice West: Would do it today, but my day is kind of crazy, unfortunately.

325
00:28:43.530 --> 00:28:46.100
Tom McGovern: My goal at Erin, Justice, is that

326
00:28:46.250 --> 00:28:52.650
Tom McGovern: once Aaron says, Tom, they're all flowing across, they're looking good, I'm seeing them in dev, Or tasked.

327
00:28:52.880 --> 00:29:09.260
Tom McGovern: I can… let's have some of the support people go in, and I want them to… we'll look at it, Shai and I will. We want some of the support people to go in there and start, like I mentioned, just getting socialized with it, and going, oh yeah, I remember this from Tom seeing you, showed us the screens and stuff like that, we got an idea of it. Now I want you guys to go in and actually

328
00:29:09.380 --> 00:29:11.340
Tom McGovern: Pretend you're actually doing one.

329
00:29:11.850 --> 00:29:20.160
Tom McGovern: As if it was a real one that was starting in there, over and over. As long as it doesn't… remember, I don't want anything going out to customers or anything going externally. Either they're in their production.

330
00:29:22.150 --> 00:29:31.050
Tom McGovern: I don't want to type in an email address, and it auto-responds back to the customer, says, thank you for your ticket, here is your one oncology link, or anything like that.

331
00:29:31.810 --> 00:29:44.140
aaronbanister: So, quick note in general on, emails in the subprod instances, they are disabled just across the board, so no matter if it's you guys or incidents or whatever, no emails leave.

332
00:29:44.520 --> 00:29:45.110
aaronbanister: test.

333
00:29:45.210 --> 00:29:45.960
aaronbanister: That's my experience.

334
00:29:45.960 --> 00:29:48.839
Tom McGovern: what other customers I work with. Yep. Yep. Systems.

335
00:29:49.000 --> 00:29:54.370
aaronbanister: If any emails were to trigger under normal circumstances, say.

336
00:29:54.510 --> 00:30:13.160
aaronbanister: you know, you send a comment, in production, and, like, that would have triggered an email. You should still see that in the activity stream in the dev instance. Like, you'll see that an email was generated, it just won't… it won't have been sent. So if you see an email was generated in the activity stream of a case.

337
00:30:13.410 --> 00:30:21.230
aaronbanister: that would indicate to you that, oh, this would have triggered an email in real life if this was in production. So that would be something just to flag, if you saw it.

338
00:30:21.390 --> 00:30:22.100
Tom McGovern: Will do.

339
00:30:26.220 --> 00:30:27.050
Tom McGovern: Alright.

340
00:30:28.070 --> 00:30:29.699
Suchaya Laddaphan: We are overtime.

341
00:30:30.500 --> 00:30:31.989
Tom McGovern: I think we have our plans, Achaya.

342
00:30:32.220 --> 00:30:35.670
Justice West: Yep, I gotta run, too. It's actually, Nick, Tom.

343
00:30:35.790 --> 00:30:36.720
Justice West: Oh, good.

344
00:30:36.720 --> 00:30:40.829
Tom McGovern: I'm… I… good, because I have him in a half hour, so if he goes over, I know who he's with, so…

345
00:30:40.830 --> 00:30:43.239
Justice West: That's right. All right. Alright, talk to you guys later. Take care.

346
00:30:43.650 --> 00:30:45.250
Suchaya Laddaphan: Thank you. Bye. Bye.

347
00:30:45.250 --> 00:30:46.439
Tom McGovern: So, Chai, you wanna hang on?

348
00:30:47.100 --> 00:30:49.110
Suchaya Laddaphan: Sure, one second, let me stop the recording.