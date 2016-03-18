# comp2106-lesson8
Enabling Passport Local and GitHub for Authentication

Note the change in routes/articles.js - instead of calling isLoggedIn function (which does not work) we are checking if the req.isAuthenticated right in the GET handler

router.get('/add', function(req, res, next) {

    // new
    if (req.isAuthenticated()) {
        res.render('articles/add', {
            title: 'Add a New Article'
        });
    }
    else {
        res.redirect('/auth/login');
    }
/* old
    res.render('articles/add', {
        title: 'Add a New Article'
    });*/
});
