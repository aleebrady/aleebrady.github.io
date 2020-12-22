---
layout: post
title:      "React-ion to React-Redux Project"
date:       2020-12-22 13:37:48 -0500
permalink:  react-ion_to_react-redux_project
---

These last several months been a long hard road of struggles and learning. This project was no different. It tested the things I know and I should know, and gives me an idea of things that need to be reinforced and developed. I also have the motivation to continue building more projects (React and Rails) as I continue developing as a developer. 

When choosing a domain, I stuck with something I was totally comfortable with, and something that kept me going througout this entire program, working out. I started with two models, workouts and records. The backend was not too challenging, since we've been down that road since Sinatra. 

Running npx create-react-app, is where the real fun began. I started with installing all of the dependencies needed for the project: 

- react-router-dom
- react-bootstrap
- redux 
- redux-thunk 

I then wanted to setup my redux store, which I followed this methodology:

- Design the store
- Define actions
- Created Reducers
- Setup the store 

Once I had all of these elements in place, I could start building out my frontend. 

I started with my parent model and fetched all of objects from the rails api backend. Once that was successful, I could focus on creating ( POST action ) to create new workout objects to save back to the database. I continued to build out my delete action and was able to move on to the belongs to model. All methods used were pretty similar to the lessons leading up to project week. For example the handleOnChange and handleOnDelete methods: 

```
class WorkoutInput extends React.Component {

    state = {name: ""}

    handleOnChange = (event) => {
        this.setState({[event.target.name]: event.target.value})
    }

    handleOnSubmit = (event) => {
        event.preventDefault()
        this.props.addWorkout(this.state)
        this.setState({name: "", 
        focus: "", 
        description: ""})
    }
```

I did the same for the child model, and built it out almost the same way for simplicity sake:

```
class RecordmarkInput extends React.Component {

    state = {name: "", 
    link: "", 
    notes: ""}

    handleOnChange = (event) => {
        this.setState({[event.target.name]: event.target.value})
    }

    handleOnSubmit = (event) => {
        event.preventDefault()
        this.props.addRecordmark(this.state, this.props.workout.id)
        this.setState({name: "", link: "", notes: ""})
    }
```

As I completed building out my components, I imported those components into their container for each model. Where I implemented mapStateToProps methods: 

```
const mapStateToProps = state => {
    return {
        workouts: state.workouts
    }
}

export default connect(mapStateToProps, {fetchWorkouts})(WorkoutsContainer)
```

After connecting all of the moving parts with a lot help and research, I was about to add some styling and utilize react-bootstrap. I really enjoyed different ways to implement images into the project. Keeping things simple, I used the public folder method. Although I will want to become efficent using the .svg files for a better presentation:

```
SVG: 
import Logo from '../logo.svg'
<img src={Logo} width="500" alt="logo" />

PUBLIC:
 <img src={process.env.PUBLIC_URL + "/logo.png"} width="200" alt="logo" /><br></br>
```

Once everything was tinkered with, I settled on the color scheme used for the project. I also tinkered with some some deconstruction in on of my components. 

```
const Workouts = ({ workouts, deleteWorkout }) => {

    const handleDelete = ({ id }) => {
        deleteWorkout(id)
    }

    return( 
        <div className="container">
            <h1>All Workouts</h1>
            <img src={process.env.PUBLIC_URL + "/barbell.png"} width="200" alt="logo" /><br></br>
            {workouts.map(workout =>
            <ListGroup>
                <ListGroup.Item>
                    <h5><Link to={`/workouts/${workout.id}`}>{workout.name}</Link></h5>
                    <h6>{workout ? workout.recordmarks.length === 1 ? `${workout.recordmarks.length} Recordmark` : `${workout.recordmarks.length} Recordmarks` : null}</h6>
                    <p><i>{workout.description}</i></p>
                    <Button variant="danger" onClick={e =>
                    window.confirm('Delete workout and all associated benchmarks?') &&
                    handleDelete(workout)
                    } type="submit">Delete Workout
                    </Button>
                </ListGroup.Item>
                <br />
            </ListGroup>
            )}
        </div>
    )

}

```
VS
```
const Workouts = ({ props }) => {

    const handleDelete = ({ workout }) => {
        deleteWorkout(workout.id)
    }

    return( 
        <div className="container">
            <h1>All Workouts</h1>
            <img src={process.env.PUBLIC_URL + "/barbell.png"} width="200" alt="logo" /><br></br>
            {props.workouts.map(workout =>
            <ListGroup>
                <ListGroup.Item>
                    <h5><Link to={`/workouts/${workout.id}`}>{workout.name}</Link></h5>
                    <h6>{workout ? workout.recordmarks.length === 1 ? `${workout.recordmarks.length} Recordmark` : `${workout.recordmarks.length} Recordmarks` : null}</h6>
                    <p><i>{workout.description}</i></p>
                    <Button variant="danger" onClick={e =>
                    window.confirm('Delete workout and all associated benchmarks?') &&
                    handleDelete(workout)
                    } type="submit">Delete Workout
                    </Button>
                </ListGroup.Item>
                <br />
            </ListGroup>
            )}
        </div>
    )

}
```

After completing on things that needed and I wanted to be completed, I totally understand there's a lot more to learn about React, I will continue to learn more about hooks and context APIs, just for starters. My overall experience of this program has been humbling to say the least, but I have absored a wealth of knowledge which I could not fathom I could, but the learning will continue as I go. 

Thank you for reading. 














