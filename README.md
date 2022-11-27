# FAQ

## How do I add a post to the blog?

It's really easy! Just create a new `.markdown` file in the style of the existing files under [`_posts`](https://github.com/ucl-dark/blog.ucldark.com/tree/master/_posts). Your post should be written in standard markdown in this file. Make sure that `layout: post`, `title: <your title>`, `date: <publication date>`, where
	- The name of your `.markdown` file should be in the format `YYYY-MM-DD-<short_name>.markdown`, where the `<short_name>` should be all lowercase and use `_` for spaces.
	- `<publication date>` should be of the form `YYYY-MM-DD 8:00:00 +0000` format. Note that the time component does not matter, so as a standard, we will default to `8:00:00 +0000`.
	- `title` should make use of standard title capitalization style (e.g. following APA standards). This means capitalizing all words except for standard conjunctions, prepositions under 4 letters, and proper nouns that take on lowercase by definition. This site will help you automatically follow this convention: [https://capitalizemytitle.com/](https://capitalizemytitle.com/).

## How do I add images and videos to my post?

If your post has static assets like images or video, do the following:
- Create a new folder under (`assets/post_assets`)[https://github.com/ucl-dark/blog.ucldark.com/tree/master/assets/post_assets] with the same name as the `<short_name>` component of your post `.markdown`, i.e. without the time stamp part. Your post assets like images and videos will go in here.
- Link in images the same way you normally would in markdown: `![<placeholder image description>](/assets/post_assets/<short_name>/<your_image_name>.png)`.
- Link in videos as follows (but ideally make the video file < 10 MB):
```
<video width="100%" autoplay muted loop playsinline>
  <source src="/assets/post_assets/<short_name>/<your_video_name>.mp4">
</video>
```
- **Whenever possible, use `.mp4` instead of `.gif`, which are much larger files.**

## My post already exists at another URL. How can I make a post that redirects to that URL?

- Create a post `.markdown` as usual, but with an empty post body below the config section.
- Add an additional config, `redirect_url: <absolute_url>` below the `title` config. The post will redirect to the `<absolute_url>` of your existing post.

## How do I publish the new post?

The blog is automatically rebuilt whenever the `master` branch is updated. So to update the blog with your post do the following:

```
git add . -A
git commit -m '<your commit message describing your post>'
git push origin master
```

**As such, please use a separate branch to manage any intermediate work on your post and merge in your final changes before pushing to master!**

For additional questions, suggestions, and feedback, get in touch with Minqi.
