# msm-gui

Target: https://msm-gui.matchthetarget.com/

Video: https://share.descript.com/view/aGvwjU9hVXx

Git commit: https://github.com/demostudent24/msm-gui/commits/main

Lesson: https://learn.firstdraft.com/lessons/129

Grading info: https://grades.firstdraft.com/resources/eeef6b17-b251-4945-9d12-89414d90e56d

<hr>

Notes

1. Populate tables with data using the command `rake sample_data`.
2. You can view the populated table here: https://cautious-bassoon-w9rpxpqg49xf5495-3000.app.github.dev/rails/db.
3. Create forms for directors, movies, and actors routes. Set the route for the form. 
4. Set the route within config/routes.rb, as follows.

```
  post("/insert_movie_record", {:controller=> "movies", :action => "create"})
```

5. (7 min) Accordingly add the create method within `app/controllers/movies_controller.rb`. (12 min) - destroy useless data from database
6. You may review the current dataset by going to https://cautious-bassoon-w9rpxpqg49xf5495-3000.app.github.dev/rails/db
7. To destroy the useless data containing value 1 through 6, type inthe debug console a_movie.destroy. You can then check the data in the table by visiting the .../rails/db dataset.
8. To reinitialize the data in the table, type rake sample_data.
9. (18 min) Add an if-else statement to the app/controllers/views/movie_templates/index/html.erb file as follows:
```
<td>
  <% matching_directors = Director.all.where({ :id => a_movie.director_id }) %>
  
  <% the_director = matching_directors.at(0) %>

  <% if the_director == nil %>
    Uh oh! We weren't able to find a director for this movie.
  <%else%>
    <%=the_director.name%>
  <%end%>
</td>
```
10. (21 min) Added delete button for movies.
