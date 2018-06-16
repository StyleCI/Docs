# Change Log

## 14/04/2018 - April Fixer Updates

We've just deployed a major round of fixes and improvements to our fixers. Most notably, the following new PHP fixers have been added:

* `array_indentation`,
* `comment_to_phpdoc`,
* `date_time_immutable`,
* `fully_qualified_strict_types`,
* `no_alternative_syntax`,
* `php_unit_ordered_covers`,
* `php_unit_set_up_tear_down_visibility`,
* `standardize_increment`,
* `string_line_ending`.

Out of these fixers, `comment_to_phpdoc`, `date_time_immutable`, `php_unit_set_up_tear_down_visibility`, `self_accessor`, and `string_line_ending` are risky.

Finally, the long deprecated "linting" config option has now been removed.

## 14/04/2018 - Beta Programme Closes

As of today, we have officially terminated our beta programme.

Thanks to everyone who took part!

## 12/04/2018 - Analysis Screen Update

We've made some tweaks to the analysis screen. Importantly, StyleCI now shows the number of files analyzed, and the time taken to fetch and analyze the code. This should make debugger your config files much easier, knowing if the build only passed because 0 files where analyzed.

## 07/04/2018 - Deploy Keys Update

As of today, StyleCI no longer uses deploy keys due to their unreliability on GitHub. Please let us know if you see any issues with our new strategy that uses HTTPS with the OAuth2 token.

## 29/01/2018 - Happy New Year!

We kick off 2018 by launching support for JavaScript, JSX, Typescript, CSS, SCSS, Less, and Vue.js. You can find our documentation at https://styleci.readme.io/docs/multi-lang, and our blog post at https://blog.alt-three.com/javascript-css-and-vue-js-launch/.

We've also fixed a few bugs in our PHP fixing platform, and added the following new fixers:

* `backtick_to_shell_exec`,
* `multiline_comment_opening_closing`,
* `newline_before_semicolons_chained`.

## 10/12/2017 - December Updates

We've added the following new fixers:

* `const_separation`
* `escape_implicit_backslashes`
* `explicit_indirect_variable`
* `explicit_string_variable`
* `final_internal_class`
* `method_chaining_indentation`
* `property_separation`
* `static_lambda`

Out of these fixers, `final_internal_class` and `static_lambda` are risky. We've also added the `const_separation` and `property_separation` to the `symfony` preset.

As always, details of each fixer can be found on the fixer docs page.

## 11/11/2017 - November Updates 2

Due to feedback on our October update, the minimality of the `align_double_arrow` and `align_equals` fixers has been moved to two new fixers:

1. `align_double_arrow_minimal`,
2. `align_equals_minimal`.

Please get in touch with us if you have any questions or feedback.

## 06/11/2017 - November Updates 1

There are various changes to be aware of:

1. The `no_tab_indentation` fixer has been renamed to `indentation`, however, using it's old name will continue to work for now.
2. The PHP 7.1 `compact_nullable_typehint` fixer is now available.
3. The `post_increment` fixer is now available, and is enabled on the `laravel` and `recommended` presets.
4. Various new PHPUnit fixers are now available, to aid with migration to newer versions. These are `php_unit_expectation`, `php_unit_mock`, `php_unit_namespaced`, and `php_unit_no_expectation_annotation`. All of these fixers are marked as heuristic.

## 30/10/2017 - Beta Programme Launch

We're proud to announce the availability of our JavaScript private beta, adding support for JavaScript, Flow, JSX, TypeScript, CSS, SCSS, and Less.

Our full blog post is available at https://blog.alt-three.com/javascript-private-beta/, where you can sign-up for the beta programme.

## 28/10/2017 - October Updates

In today's fixer platform deployment, we announce immediate availability of the `yoda_style` fixer, to convert comparison expressions to use the yoda format: https://en.wikipedia.org/wiki/Yoda_conditions. This fixer is now enabled in our `symfony` preset.

There is also a new fixer `no_homoglyph_names` that will replace accidental usage of homoglyphs in names, by which we mean, will remove non-asci characters from names. For obvious reasons, this fixer has been marked as risky.

Finally, the `align_double_arrow` and `align_equals` fixers will now perform a minimal possible alignment instead of aligning to the right most operator.

## 26/08/2017 - August Updates 2

Today we deploy our second round of fixer releases and bug fixes. Notable changes are fixes to movement of comments, and the introduction of the new `no_unneeded_curly_braces` and `no_unneeded_final_method` fixers.

## 12/08/2017 - August Updates 1

We've shipped our latest round of bug fixes, and some new fixers and preset changes.

We introduce 8 new fixers:

* `align_comments`
* `align_phpdoc`
* `blank_line_before_break`
* `blank_line_before_continue`
* `blank_line_before_declare`
* `blank_line_before_throw`
* `blank_line_before_try`
* `no_superfluous_elseif`
* `phpdoc_types_order`

We've added all the new blank line fixers into the `symfony` preset, the `align_phpdoc` fixer into the `laravel` and `recommended` presets, and also the `blank_line_before_throw` and `blank_line_before_try` fixers into the `recommended` preset.

## 01/08/2017 - GitHub Marketplace

StyleCI has launched on the GitHub Marketplace. It was a pleasure to work with the GitHub staff to make this happen. It's now easier than never to get started with StyleCI.

The associated blog post is available at https://blog.alt-three.com/github-marketplace-launch/

## 24/06/2017 - June Updates 3

As well as fixing some bugs, we've added the `no_null_property_initialization` fixer which ensures that properties are not explicitly initialized with `null`. No changes have been made to any of the presets.

## 17/06/2017 - June Updates 2

We've added the `doctrine_annotation_array_assignment` fixer which normalizes Doctrine operator assignment in arrays. No changes have been made to any of the presets.

## 08/06/2017 - June Updates 1

As well as some performance improvements, a new risky fixer `void_return` is now available. This fixer, targeted at PHP 7.1, will add the void return type to functions with missing or empty return statements. No changes have been made to any of the presets.

## 29/04/2017 - April Updates

We've added the following new fixers:

* `doctrine_annotation_braces`
* `doctrine_annotation_indentation`
* `doctrine_annotation_spaces`
* `function_to_constant` (*risky*)
* `long_list_syntax`
* `magic_constant_casing` (symfony, laravel, recommended)
* `non_printable_character` (*risky*)
* `php_unit_test_class_requires_covers`
* `short_list_syntax`

## 24/03/2017 - March Updates

We've added the following new fixers:

* `is_null` (*risky*)
* `native_function_invocation` (*risky*)
* `phpdoc_no_useless_inheritdoc` (symfony, laravel, recommended)
* `phpdoc_return_self_reference` (symfony)
* `ternary_to_null_coalescing`

We've also marked the `no_unreachable_default_argument_value` fixer as *risky*, in light of the PHP 7.1 semantics.

## 22/01/2017 - Symfony Tweak

The `simplified_null_return` fixer has been removed from the `symfony` preset.

## 15/01/2017 - Minor Improvements

Today brings some more improvements to our analysis platform.

Notable changes for users are:

* The `no_alias_functions` fixer is now marked as "risky".
* `no_unreachable_default_argument_value` is no longer part of the `symfony` preset.

## 14/12/2016 - Slack Support

StyleCI can now send Slack notifications for enabling & disabling of repos as well passing & failing analyzes.

The associated blog post is available at https://blog.alt-three.com/styleci-slack/.

## 12/12/2016 - PHP 7.1 Support

More exciting news. Today we launch support for PHP 7.1! Check it out now!

The associated blog post is available at https://blog.alt-three.com/php-7-1-support/.

## 04/12/2016 - Major Fixer Updates

We're excited to announce some major improvements to our fixers and presets, and finally, the `length_ordered_imports` fixer!

Our 16 new fixers are:

* `const_visibility_required`
* `length_ordered_imports`
* `no_blank_lines_after_return`
* `no_blank_lines_after_throw`
* `no_blank_lines_between_imports`
* `no_blank_lines_between_traits`
* `no_extra_block_blank_lines`
* `no_spaces_outside_offset`
* `php_unit_fqcn_annotation`
* `phpdoc_add_missing_param_annotation`
* `phpdoc_link_to_see`
* `pow_to_exponentiation`
* `property_visibility_required`
* `protected_to_private`
* `return_type_declaration`
* `single_line_class_definition`

Full descriptions of each fixer are available in our docs.

The following new fixers have been added to the `symfony` preset:

* `no_blank_lines_after_throw`
* `no_blank_lines_between_imports`
* `no_extra_block_blank_lines`
* `no_spaces_outside_offset`
* `php_unit_fqcn_annotation`
* `phpdoc_link_to_see`
* `property_visibility_required`
* `return_type_declaration`
* `single_line_class_definition`

The following new fixers have been added to the `laravel` preset:`

* `length_ordered_imports`
* `no_blank_lines_after_throw`
* `no_blank_lines_between_imports`
* `no_blank_lines_between_traits`
* `property_visibility_required`

The following new fixers have been added to the `recommended` preset:

* `no_blank_lines_after_throw`
* `no_blank_lines_between_imports`
* `no_blank_lines_between_traits`
* `no_spaces_outside_offset`
* `property_visibility_required`

Our other changes include:

* The part of the `no_extra_consecutive_blank_lines` fixer that removed newlines between imports has been moved to the new `no_blank_lines_between_imports` fixer.
* We've renamed the `ordered_imports` fixer to `alpha_ordered_imports`. The original name will continue to work.
* We've rename and the `visibility_required` fixer to `method_visibility_required`. The original name will continue to work.
* We've merged into the `psr0` fixer into the `psr4` fixer.
* The new `pow_to_exponentiation` fixer is "risky".
* The `simplified_null_return` fixer has been marked as "risky" in light of the changes made in PHP 7.1.
* Support for PHP 7.0 grouped imports.
* Various bug fixes, of course.

You can read our blog post at https://blog.alt-three.com/imports-by-length/.

## 30/11/2016 - Plan Recommendations

When trying to perform an action outside of your plan, StyleCI will now recommend the cheapest upgrade path for you. Hopefully this will prevent confusion, and allow for a smoother experience.

## 23/11/2016 - Changed Commit Messages

By popular request, we've now changed our commit messages to use the present tense. A small change, but makes a difference all the same.

## 18/09/2016 - Various Small Improvements

The settings button for a repo will now show for all users, and will present a friendly error to the user indicating that they are not an admin, if required. This is a significant improvement on previously when a hard error page would be displayed, and the settings button would just be missing.

The fact that branch enabling and disabling will now show up to non-admins too, rather than being hidden, however, it will request that the user should contact a repo admin to disable the branch. Previously, the availability of this feature was hidden from non-admin users.

We've lowered the default notification level to "some", rather than "all" for new users. This is due to user feedback saying only notifications relevant to them were important, rather than all notifications from the repositories they were collaborating on. This setting can be modified on the profile tab of the account page: https://styleci.io/account#profile.

## 10/09/2016 - Account Page Improvements

We've just deployed some great improvements to our account page, significantly improving performance. We hope the new snappier interface will allow you to work more quickly.

## 27/08/2016 - Linting Changes

Starting from today, it is no longer possible to disabling linting, and the linting config option is officially deprecated. Setting it to false will cause a configuration error, and for now, setting it to true is still permitted, but is not required.

## 27/08/2016 - Three New Fixers

Today, we announce the availability 4 new fixers:

* `class_keyword_remove`
* `mb_str_functions`
* `silenced_deprecation_error`

Full details are available on our docs.

Note that both our new `mb_str_functions` and `silenced_deprecation_error` fixers are "risky", and new `silenced_deprecation_error` fixer has been added to the `symfony` preset.

## 07/08/2016 - New Constant Fixer

As well as fixing various bugs, today, we announce the availability of a new `uppercase_constants` fixer. This fixer will ensure native constants such as `TRUE` and `FALSE` are uppercased. This fixer is essentially the opposite of the `lowercase_constants` fixer.

## 25/07/2016 - Various PR Changes

We're excited to announce an important change to the way we analyze PRs. Going forward, we now limit the files analyzed to those modified by the pull request you've made.

In order to make a clear distinction between PR and push analyzes, we are now using a different "status context", just like Travis CI does. This is perfect for if you are partially phasing in some coding standards changes, or are accepting PRs from forks that haven't been rebased in a while.

In addition to this, whenever we sent a new fix pull request to a branch, we will also close any existing fix PR open on that branch. This will prevent having a large amount of spam PRs on your repos.

You can read the full details on our blog: https://blog.alt-three.com/new-pr-analysis-system/.

## 25/06/2016 - Fixer Improvements

We're delighted to announce five new fixers:

* `declare_equal_normalize`
* `declare_strict_types`
* `phpdoc_annotation_without_dot`
* `semicolon_after_instruction`
* `single_class_element_per_statement`

Full details of these can be found in our docs.

The following new fixers have been added to the `symfony` preset:

* `declare_equal_normalize`
* `phpdoc_annotation_without_dot`
* `single_class_element_per_statement`

The following new fixers have been added to both the `laravel` and `recommended` presets:

* `declare_equal_normalize`
* `single_class_element_per_statement`

It should also be noted that the new `declare_strict_types` is "risky", and that the `no_whitespace_in_blank_lines` fixer has been renamed to `no_whitespace_in_blank_line`, though, you can still use the old name if you wish.

## 06/06/2016 - Fixer Updates

We're delighted to announce the availability of a new fixer: `normalize_index_brace`. This fixer ensures that array indexes are always written by using square braces, rather than the exotic curly braces syntax. This fixer has been included in our `symfony`, `laravel`, and `recommended` presets.

As always, various bugs have been fixed, such as some false positives in the empty comment remover, and some edge cases with parentheses removal affecting clone statements.

## 05/06/2016 - Direct Fix Pushing

I'm delighted to announce two new automation capabilities in StyleCI. We've introduced an option for StyleCI to directly commit our fixes to your code and skip the pull request out entirely. We've also added an option to squash its fix pull requests when automatic merging is enabled.

You can read the full details on our blog: https://blog.alt-three.com/direct-fix-pushing/.

## 28/05/2016 - Fixer Updates

The long awaited `no_useless_else` fixer is finally here, and will remove else blocks wherever they are redundant. In addition to this, the `dir_constant`, `modernize_types_casting`, and `random_api_migration` have been marked as risky.

Some other changes are that the `no_duplicate_semicolons` fixer has be combined into the `no_empty_statement` fixer, and, for now, the `no_blank_lines_between_uses` fixer has been combined into the `no_extra_consecutive_blank_lines` fixer. 

We're also happy to announce that various bugs have been fixed too, including some problems with the braces fixer, and the self assessor fixer with anonymous classes.

Five months ago, we announced the launch of our free Student Plan with access to StyleCI for up to five private repositories. Today we announce that we are extending this even further with our new Student Discount Scheme.

The way this works is, as well as having access to our free Student Plan, our Student Discount Scheme also entitles you to upto 50% off all our other plans too. This can be a big help when you want to collaborate in student teams using GitHub organizations, or simply need more repositories, at super low cost.

You can read the full details on our blog: https://blog.alt-three.com/student-discount-scheme/.
