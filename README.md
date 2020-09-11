# flix_codepath

Flix is an app that allows users to browse movies from the [The Movie Database API](http://docs.themoviedb.apiary.io/#).

```
let url = URL(string: "https://api.themoviedb.org/3/movie/now_playing?api_key=a07e22bc18f5cb106bfe4cc1f83ad8ed")!
let request = URLRequest(url: url, cachePolicy: .reloadIgnoringLocalCacheData, timeoutInterval: 10)
let session = URLSession(configuration: .default, delegate: nil, delegateQueue: OperationQueue.main)
let task = session.dataTask(with: request) { (data, response, error) in
   // This will run when the network request returns
   if let error = error {
      print(error.localizedDescription)
   } else if let data = data {
      let dataDictionary = try! JSONSerialization.jsonObject(with: data, options: []) as! [String: Any]

      // TODO: Get the array of movies
      // TODO: Store the movies in a property to use elsewhere
      // TODO: Reload your table view data

   }
}
task.resume()
```

---

## Flix Part 1

### User Stories

#### REQUIRED (10pts)
- [x] (2pts) User sees an app icon on the home screen and a styled launch screen.
- [x] (5pts) User can view and scroll through a list of movies now playing in theaters.
- [x] (3pts) User can view the movie poster image for each movie.

#### BONUS
- [x] (2pt) User can view the app on various device sizes and orientations.
- [x] (1pt) Run your app on a real device.

### App Walkthrough GIF
<img src="https://res.cloudinary.com/headincloud/image/upload/v1599202263/flix_gif_nxvtgv.gif" width=250><br>
<img src="https://res.cloudinary.com/headincloud/image/upload/v1599202363/flix_liedown_gif_mfwy7n.gif" width=250><br>

### Notes
Describe any challenges encountered while building the app.
- Understanding the API.

---

## Flix Part 2

### User Stories

#### REQUIRED (10pts)
- [x] (5pts) User can tap a cell to see more details about a particular movie.
- [x] (5pts) User can tap a tab bar button to view a grid layout of Movie Posters using a CollectionView.

#### BONUS
- [x] (2pts) User can tap a poster in the collection view to see a detail screen of that movie.
- [ ] (2pts) In the detail view, when the user taps the poster, a new screen is presented modally where they can view the trailer. (Done partially :/)

### App Walkthrough GIF
(required part):

<img src="https://res.cloudinary.com/headincloud/image/upload/v1599804754/flix_week2_required_k1crck.gif" width=250><br>

(first bonus part):

<img src="https://res.cloudinary.com/headincloud/image/upload/v1599804876/flix_week2_bonus_pndmfm.gif" width=250><br>

### Notes
Describe any challenges encountered while building the app.
- The second bonus about presenting modally is pretty challenging. I need to go over the doc again, and see what I have been missing. Also, some parts have been deprecated, but I can see the trace of the updated things, and I was trying my best to guess the best solution.
- I tried to add tap gesture to the view controller,and then, also to the posterView, but neither of them would work.
