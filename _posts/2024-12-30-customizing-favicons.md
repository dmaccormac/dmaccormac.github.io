---
title: A browser agnostic approach to customizing favorite icons
date: 2024-12-30
last_modified_at: 2024-12-31
tags: web accessibility favicon favman
excerpt: Favman is a tool to easily create HTML bookmark files with custom icons.
---

# Introduction

Research on the use of visual aids, such as color coding, in improving human-computer interaction has demonstrated the significant value of these tools [1]. Such elements help to make digital interfaces more accessible, intuitive, and usable for a broader range of users, including those with disabilities [2, 3].

This article outlines a current accessibility challenge faced in relation to website icons, examines existing solutions to the problem and proposes a new browser agnostic solution. Finally, the proposed solution is implemented using a small Windows based graphical application to test the approach.

# Challenges in customizing favicons

The favicon, short for favorite icon, is the small, distinctive image associated with a website, often displayed in browser tabs, bookmarks, and address bars. While favicons are crucial for branding and quick visual recognition, changing or customizing them for bookmarks can be difficult for end-users, especially without resorting to third-party extensions. This issue highlights the limitations in modern web browsers' native capabilities when it comes to managing or customizing these icons.

This limitation can be problematic for users who wish to organize their bookmarks with custom icons (for visual clarity, aesthetics, or better usability). For instance, users with visual impairments, or those who have a large number of bookmarks, might find it difficult to quickly differentiate between similar icons.

There are several reasons why browsers do not natively allow users to change favicons for bookmarks:

- Security: Allowing users to arbitrarily change favicons could introduce security risks. 
- Consistency: To maintain a consistent experience for all users according to the website’s own configuration. 
- Technical: Requires adding features that could complicate the browser’s architecture and performance.

# Current approaches

To overcome this limitation, users often turn to third-party browser extensions. These extensions provide additional functionality that browsers don’t offer natively. 

Popular extensions like Bookmark Favicon Changer for Chrome allow users to manually upload or select custom icons for their bookmarks.The approach typically work by modifying the bookmark entries on the local level, essentially replacing the favicon image with one chosen by the user. 

While these extensions can provide a solution to the problem, they also come with certain challenges.

- Security: Third-party extensions often require access to users’ browsing data. 
- Updates: Extensions require maintenance and may break when the browser is updated.
- Compatibility: Such extensions are not available for all browsers.

# Our approach

Our approach builds on the existing research to date, but uses the browser agnostic approach of creating a local redirect file with a custom icon. This approach removes the need to add third party extensions to the browser, and provides a single solution that works across all environments. 

The proposed solution uses a HTML redirect with a custom `<link>` element. 

```html
<link rel="icon" href="example.ico" type="image/x-icon">
```

The `<link>` element is a HTML tag used to define a relationship between the current HTML document and an external resources. The `rel` attribute defines the relationship between the document and the resource. In this case, the `icon` attribute tells the browser that the linked resource is an icon file, to be used a favicon for the website. The `type` attribute specifies the MIME type (media type) of the linked file.

A complete example is shown below:

```html
<!DOCTYPE html>
<html>
<head>
    <title>GitHub</title>
    <link rel="icon" href="GitHub.ico" type="image/x-icon">
    <meta http-equiv="refresh" content="0;url=https://github.com/dmaccormac">
</head>
<body>   
    <p>Redirecting to <a href="https://github.com/dmaccormac">https://github.com/dmaccormac</a>
</body>
</html>
```

## Implementation

To test the proposed approach, we created a small tool for Windows - Favman - which allows you to easily create HTML bookmark files with custom icons. A screenshot is shown below.

![Create a bookmark using a custom icon with Favman](/assets/images/2024-12-30-customizing-favicons-1.png)

![Example bookmark with custom icon](/assets/images/2024-12-30-customizing-favicons-2.png)

Enter a title, URL and icon file, click `Create` and Favman will generate the custom bookmark. Output files are saved to the `%APPDATA%\Favman\Bookmarks` directory. The bookmark will be automatically opened in the default browser if the `Open bookmark` checkbox is enabled. 

When the bookmark is opened, there is a default timeout of 5 seconds before the redirect occurs. This is to allow time for the user to bookmark the page. You can press `Ctrl + D` to quickly bookmark the page before the redirect occurs.

The application is available on the project GitHub page [here](https://github.com/dmaccormac/favman).

## Limitations

There are some inherent limitations to this approach. 
- Once the custom bookmark item completes the redirect action, the favicon of the target site will be displayed in the tab title bar. 
- Adjusting the redirect timeout requires some technical capabilities which could pose a challenge for some users. 
- While the timeout can be set to the minimum value by editing the HTML file, the redirect page will still be briefly visible to the end user.   

## Further work

 Initial testing highlighted several areas with opportunities for improvement. This implementation lays the groundwork for future developments such as support for multiple icon sizes and formats, the ability to modify existing items, and adding more granular customization options. 

# Conclusion

Visual aids are indispensable in the design of accessible digital interfaces, particularly for users with disabilities. Icons, colors, contrast, and structured layouts can make systems more intuitive, reduce cognitive load, and support diverse interaction methods. Incorporating these elements into designs not only improves accessibility but also enhances the overall user experience. Testing the proposed solution using the Favman implementation demonstrated that this approach provides a viable solution, with some inherent limitations.

# References

[[1] M. Zhang, Y. Gong, R. Deng, and S. Zhang, “The effect of color coding and layout coding on users’ visual search on mobile map navigation icons,” Frontiers in Psychology, vol. 13, Dec. 2022, doi: https://doi.org/10.3389/fpsyg.2022.1040533.](https://doi.org/10.3389/fpsyg.2022.1040533)

[[2] Sara Hamideh Kerdar, L. Bächler, and Britta Marleen Kirchhoff, “The accessibility of digital technologies for people with visual impairment and blindness: a scoping review,” Discov Computing, vol. 27, no. 1, Aug. 2024, doi: https://doi.org/10.1007/s10791-024-09460-7.](https://doi.org/10.1007/s10791-024-09460-7)

[[3] S. Shethia and A. A. Techatassanasoontorn, “Experiences of People with Visual Impairments in Accessing Online Information and Services: A Systematic Literature Review,” Pacific Asia Journal of the Association for Information Systems, pp. 39–66, 2019, doi: https://doi.org/10.17705/1pais.11203.](https://doi.org/10.17705/1pais.11203)

‌