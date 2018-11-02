---
layout: post
title:      "Just a short story about State and Props..."
date:       2018-11-02 16:49:07 +0000
permalink:  just_a_short_story_about_state_and_props
---

State and Props walk into a bar...  Neither was hurt but why didn't anyone warn them about the bar?

State and Props are JavaScript objects that pass information to and through components to influence the output of render. 

State exists only within a component - a stateful component - and is established when a component is called. It is established by “this.state” but it can only be modified by “this.setState”.  To avoid over-rendering, React  waits for all components to call setState in their event handlers before starting to render thus saving resources and increasing performance. State can be passed to another component, but it must be passed as props.  
A component should be stateful only when it needs to change the data. It can remain stateless if it only needs to read the data.

Consider a game with a timer for each player’s turn. The timer would be one component and the player would be another.  The timer would change its state every second and it would report that change to the player as props.  The player cannot change the value of the timer prop, but the timer prop can be  reset by its component and/or the store every time the state changes, every second, and that newly defined prop is passed to the player component.

Rather than being established within a component,  props (properties) are passed into a component either a stateful or a stateless component.  They are passed from a Parent component or from the store through mapStateToProps, a Redux function.  Props cannot be changed in a component - they are immutable!  However their value can be changed if the component that establishes the prop (as state) changes the value with this.setState. When the value of the state changes, the prop itself doesn’t change but instead, the store saves a new version of the prop over the old version and pushes that value to every component using that prop.  Use props when you only want to use the data, not change the data that is passed in.

Props and State allow components to share information without confusion because, when done right, they ensure there is only one point of truth and everything hinges on that truth.  Props holds the truth and is always true - if a peice of state is used in other components it is passed as props and if the state changes, so does the prop…  Whenever state is established or changed, it passes its value to the store and then, rather than changing the prop, the store creates a new version of the prop and sends that out to all components using that prop. And the truth continues…

As similar as they are, it is their differences between State and Props that make them powerful.  

