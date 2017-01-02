### Let's take a look at how the normal React components talk:

***APage***: Ok, I now create you, TabContainer and here is your list of tabs:
```
[
    {
        label: "Users",
        component: UserListComponent
    },
    {
        label: "Activities"
        ...
    }
    ...
]
```

. That's it, you had all you need, from now on you are on your own and don't ever call me back (callback), I need to handle other important business.

***TabContainer***: Ok dad, got it. Trust me I can do it all by myself and won't disturb you ever.

... TabContainer goes on and don't need to talk back to APage anymore, it handles changing tabs by itself, deciding which tab is active, which is not, tab component creation, destroying... all by itself...

### Now, let's take a look at how the components in Redux talk:

***APage***: Ok, I now create you, TabContainer and here is your list of tabs:
```
[
    {
        label: "Users",
        component: "USER_LIST"
    },
    {
        label: "Activities"
        ...
    }
    ...
]
```
. That's it, don't ever call me back...

***TabContainer***: Ok dad, I don't think I will need anything else from you, but I will need God (Redux) for many thing else.

... (a second later) ...

***TabContainer***: Oh God, user just clicked on a inactive tab header. Tell me what to do, quick...

***Redux***: Oh ok, let me look up the action list... here it is, what is the tab component name? "USER_LIST"? Let me see which data needs to go with it... 

(God murmuring to himself): No no, not `activities`, it should be `users`, how to get it... api...

***TabContainer***: ... is it done God?... What should I do?...

***Redux***: Hey, shut up, I don't talk to you, you are nothing, I just need to update the magic store and you will be transformed immediately. You are supposed to be stupid, all thinking is mine.

***TabContainer***: Oh, ok, sorry... I suppose I should play dead then.

(TabContainer shuts up and lie dead, waiting its corpse to be changed)

***Redux***: Oh, here, the data has arrived from server, let's make magic happen... Wait, where to put the data in the store? not into that `users` attribute, it is for the Dashboard component... Let put it in the `allUsers` attribute then.

... And pups, magical stars pops out and the dead beat TabContainer is transformed with it active header... But wait, where is the User list panel?

***Redux***: Hmm... hey APage, where is the `<UserList>` tag? It is supposed to be right there, under the tab headers. And don't forget to check for the `allUsers` data from my store.

***APage***: Oh, I thought just put the `<TabContainer>` tag there and it is enough?... No? then what is this `<TabContainer>` ?? ... They are just Tab headers?? dang... never mind. 

(APage Murmuring) I suppose I am going to add the `<ActivitiesList>` next too... but have to wait for Redux god to decide what data it's attached to first. Oh God... Can I just go on with my other tasks?

