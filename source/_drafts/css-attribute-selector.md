---
title: css attribute selector
tags:
---

E[foo] an E element with a "foo" attribute (CSS 2)
E[foo= "bar"] an E element whose "foo" attribute value is exactly equal to "bar" (CSS 2 )
E[foo~= "bar"] an E element whose "foo" attribute value is a list of whitespace-separated values, one of which is exactly equal to "bar" (CSS 2)
E[foo^= "bar"] an E element whose "foo" attribute value begins exactly with the string "bar" (CSS 3 )
E[foo$= "bar"] an E element whose "foo" attribute value ends exactly with the string "bar" (CSS 3 )
E[foo*= "bar"] an E element whose "foo" attribute value contains the substring "bar" (CSS 3)
E[foo|= "en"] an E element whose "foo" attribute has a hyphen-separated list of values beginning (from the left) with "en" (CSS 2 )