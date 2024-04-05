# Practice Game
###  Cracking 1 (Easy)
Our analysts have obtained password dumps storing hacker passwords. After obtaining a few plaintext passwords, it appears that they overlap with the passwords from the rockyou breach. Can you crack them?

| User | Password Ciphertext | Answer |
| :---: | :---: | :---: |
| Elliot | f4b5ad645707887c1359cd80f218b23a | taz2tam |
| Lindsay | bd9058d30a341f445d3d95094dfb6625 | clas206 |
| Tom | f9d9e8a3400efa01ef0c0f5960caf2e2 | ELISAMA12 |

`hashcat -m 0 cracking-1-easy.hash -a 0 /usr/share/wordlists/rockyou.txt -o cracking-1-easy.txt`

---
###  Cracking 2 (Easy)
Our analysts have obtained password dumps storing hacker passwords. Try your hand at cracking them.

| User | Password Ciphertext | Answer |
| :---: | :---: | :---: |
| Chris | 055DDC4A1B8A6C4609752A3293831D17:24E9CBA6EB8284A79CF409DEC0657171 | vehoca49 |
| Lindsay | C730D4DD130DA904C81667E9D738C5D9:92C6B07C3C27F755079F13C808A5A0CF | abatux96 |
| Ade | 6B477ADABB2D1D2F1AA818381E4E281B:A5699A73DC9A5CF7B668E0B20771D00D | olaxiv33 |

`ophcrack -g -d ~/ctf/tools/ophcrack_xp_tables -t xp_special -f cracking-2-3-easy.hash`

---
### Cracking 3 (Easy)
Our analysts have obtained password dumps storing hacker passwords. Try your hand at cracking them.

| User | Password Ciphertext | Answer |
| :---: | :---: | :---: |
| Chris | 801360B730CB0E9E25AD3B83FA6627C7:D8A78D590D1076431C1C05BA63A08E18 | ugiron20 |
| Ade | 113814160A78A3B77C3113B4A1A5E3A0:8BFEF740597379F6DA15AA333806901B | urimog87 |
| Justen | 0194F7946A79D900C81667E9D738C5D9:237FB520B8CC97AD6672AEB5476452A9 | zuyoxa76 |

`ophcrack -g -d ~/ctf/tools/ophcrack_xp_tables -t xp_special -f cracking-2-3-easy.hash`

---
###  Cracking 4 (Medium)
Our analysts have obtained a database dump. See if you can retrieve the admin password.
https://cyberskyline.com/artifact/630d3b5e3b2b0141b6aed6d0/659c4028d3da4a4d370bc01a/65fc9794cd7fd4ddf4abf2c8/62618b80a2edfea3bd0b3701/6262d8a679f6d6ced6a2ca44/download?t=3

| Question | Answer |
| :---: | :---: |
| What is the username of the admin? | carter |
| What is the hash of the admin password? | $P$BVkil0p850ufCHs.ovF/0eS96iY/hz1 |
| What is the plaintext of the admin's password? | lucky5 |

`hashcat -m 400 cracking-4-medium.hash -a 0 /usr/share/wordlists/rockyou.txt -o cracking-4-medium.txt`

```
-- phpMyAdmin SQL Dump
-- version 4.7.7
-- https://www.phpmyadmin.net/
--
-- Host: localhost:3306
-- Generation Time: Nov 06, 2018 at 10:58 AM
-- Server version: 5.6.41
-- PHP Version: 5.6.30

SET SQL_MODE = "NO_AUTO_VALUE_ON_ZERO";
SET AUTOCOMMIT = 0;
START TRANSACTION;
SET time_zone = "+00:00";


/*!40101 SET @OLD_CHARACTER_SET_CLIENT=@@CHARACTER_SET_CLIENT */;
/*!40101 SET @OLD_CHARACTER_SET_RESULTS=@@CHARACTER_SET_RESULTS */;
/*!40101 SET @OLD_COLLATION_CONNECTION=@@COLLATION_CONNECTION */;
/*!40101 SET NAMES utf8mb4 */;

--
-- Database: `carterpar_wp561`
--

-- --------------------------------------------------------

--
-- Table structure for table `wpbh_commentmeta`
--

CREATE TABLE `wpbh_commentmeta` (
  `meta_id` bigint(20) UNSIGNED NOT NULL,
  `comment_id` bigint(20) UNSIGNED NOT NULL DEFAULT '0',
  `meta_key` varchar(255) COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `meta_value` longtext COLLATE utf8mb4_unicode_ci
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;

-- --------------------------------------------------------

--
-- Table structure for table `wpbh_comments`
--

CREATE TABLE `wpbh_comments` (
  `comment_ID` bigint(20) UNSIGNED NOT NULL,
  `comment_post_ID` bigint(20) UNSIGNED NOT NULL DEFAULT '0',
  `comment_author` tinytext COLLATE utf8mb4_unicode_ci NOT NULL,
  `comment_author_email` varchar(100) COLLATE utf8mb4_unicode_ci NOT NULL DEFAULT '',
  `comment_author_url` varchar(200) COLLATE utf8mb4_unicode_ci NOT NULL DEFAULT '',
  `comment_author_IP` varchar(100) COLLATE utf8mb4_unicode_ci NOT NULL DEFAULT '',
  `comment_date` datetime NOT NULL DEFAULT '0000-00-00 00:00:00',
  `comment_date_gmt` datetime NOT NULL DEFAULT '0000-00-00 00:00:00',
  `comment_content` text COLLATE utf8mb4_unicode_ci NOT NULL,
  `comment_karma` int(11) NOT NULL DEFAULT '0',
  `comment_approved` varchar(20) COLLATE utf8mb4_unicode_ci NOT NULL DEFAULT '1',
  `comment_agent` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL DEFAULT '',
  `comment_type` varchar(20) COLLATE utf8mb4_unicode_ci NOT NULL DEFAULT '',
  `comment_parent` bigint(20) UNSIGNED NOT NULL DEFAULT '0',
  `user_id` bigint(20) UNSIGNED NOT NULL DEFAULT '0'
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;

-- --------------------------------------------------------

--
-- Table structure for table `wpbh_gf_draft_submissions`
--

CREATE TABLE `wpbh_gf_draft_submissions` (
  `uuid` char(32) COLLATE utf8mb4_unicode_520_ci NOT NULL,
  `email` varchar(255) COLLATE utf8mb4_unicode_520_ci DEFAULT NULL,
  `form_id` mediumint(8) UNSIGNED NOT NULL,
  `date_created` datetime NOT NULL,
  `ip` varchar(39) COLLATE utf8mb4_unicode_520_ci NOT NULL,
  `source_url` longtext COLLATE utf8mb4_unicode_520_ci NOT NULL,
  `submission` longtext COLLATE utf8mb4_unicode_520_ci NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_520_ci;

-- --------------------------------------------------------

--
-- Table structure for table `wpbh_gf_entry`
--

CREATE TABLE `wpbh_gf_entry` (
  `id` int(10) UNSIGNED NOT NULL,
  `form_id` mediumint(8) UNSIGNED NOT NULL,
  `post_id` bigint(20) UNSIGNED DEFAULT NULL,
  `date_created` datetime NOT NULL,
  `date_updated` datetime DEFAULT NULL,
  `is_starred` tinyint(1) NOT NULL DEFAULT '0',
  `is_read` tinyint(1) NOT NULL DEFAULT '0',
  `ip` varchar(39) COLLATE utf8mb4_unicode_520_ci NOT NULL,
  `source_url` varchar(200) COLLATE utf8mb4_unicode_520_ci NOT NULL DEFAULT '',
  `user_agent` varchar(250) COLLATE utf8mb4_unicode_520_ci NOT NULL DEFAULT '',
  `currency` varchar(5) COLLATE utf8mb4_unicode_520_ci DEFAULT NULL,
  `payment_status` varchar(15) COLLATE utf8mb4_unicode_520_ci DEFAULT NULL,
  `payment_date` datetime DEFAULT NULL,
  `payment_amount` decimal(19,2) DEFAULT NULL,
  `payment_method` varchar(30) COLLATE utf8mb4_unicode_520_ci DEFAULT NULL,
  `transaction_id` varchar(50) COLLATE utf8mb4_unicode_520_ci DEFAULT NULL,
  `is_fulfilled` tinyint(1) DEFAULT NULL,
  `created_by` bigint(20) UNSIGNED DEFAULT NULL,
  `transaction_type` tinyint(1) DEFAULT NULL,
  `status` varchar(20) COLLATE utf8mb4_unicode_520_ci NOT NULL DEFAULT 'active'
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_520_ci;

--
-- Dumping data for table `wpbh_gf_entry`
--

INSERT INTO `wpbh_gf_entry` (`id`, `form_id`, `post_id`, `date_created`, `date_updated`, `is_starred`, `is_read`, `ip`, `source_url`, `user_agent`, `currency`, `payment_status`, `payment_date`, `payment_amount`, `payment_method`, `transaction_id`, `is_fulfilled`, `created_by`, `transaction_type`, `status`) VALUES
(1, 1, NULL, '2018-10-27 20:21:09', NULL, 0, 0, '75.190.244.199', 'https://carterparsons.com/dev/tg/communities/palm-coast/', 'Mozilla/5.0 (Macintosh; Intel Mac OS X 10_14_0) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/70.0.3538.77 Safari/537.36', 'USD', NULL, NULL, NULL, NULL, NULL, NULL, 1, NULL, 'active'),
(2, 1, NULL, '2018-10-27 20:26:40', NULL, 0, 0, '75.190.244.199', 'https://carterparsons.com/dev/tg/communities/palm-coast/', 'Mozilla/5.0 (Macintosh; Intel Mac OS X 10_14_0) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/70.0.3538.77 Safari/537.36', 'USD', NULL, NULL, NULL, NULL, NULL, NULL, 1, NULL, 'active'),
(3, 1, NULL, '2018-10-27 20:28:28', NULL, 0, 0, '75.190.244.199', 'https://carterparsons.com/dev/tg/communities/palm-coast/', 'Mozilla/5.0 (Macintosh; Intel Mac OS X 10_14_0) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/70.0.3538.77 Safari/537.36', 'USD', NULL, NULL, NULL, NULL, NULL, NULL, 1, NULL, 'active'),
(4, 1, NULL, '2018-10-27 20:32:01', NULL, 0, 0, '75.190.244.199', 'https://carterparsons.com/dev/tg/communities/palm-coast/', 'Mozilla/5.0 (Macintosh; Intel Mac OS X 10_14_0) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/70.0.3538.77 Safari/537.36', 'USD', NULL, NULL, NULL, NULL, NULL, NULL, 1, NULL, 'active'),
(5, 1, NULL, '2018-10-27 20:32:18', NULL, 0, 0, '75.190.244.199', 'https://carterparsons.com/dev/tg/communities/palm-coast/', 'Mozilla/5.0 (Macintosh; Intel Mac OS X 10_14_0) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/70.0.3538.77 Safari/537.36', 'USD', NULL, NULL, NULL, NULL, NULL, NULL, 1, NULL, 'active'),
(6, 1, NULL, '2018-10-27 20:32:46', NULL, 0, 0, '75.190.244.199', 'https://carterparsons.com/dev/tg/communities/venetia-bay/', 'Mozilla/5.0 (Macintosh; Intel Mac OS X 10_14_0) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/70.0.3538.77 Safari/537.36', 'USD', NULL, NULL, NULL, NULL, NULL, NULL, 1, NULL, 'active');

-- --------------------------------------------------------

--
-- Table structure for table `wpbh_gf_entry_meta`
--

CREATE TABLE `wpbh_gf_entry_meta` (
  `id` bigint(20) UNSIGNED NOT NULL,
  `form_id` mediumint(8) UNSIGNED NOT NULL DEFAULT '0',
  `entry_id` bigint(20) UNSIGNED NOT NULL,
  `meta_key` varchar(255) COLLATE utf8mb4_unicode_520_ci DEFAULT NULL,
  `meta_value` longtext COLLATE utf8mb4_unicode_520_ci
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_520_ci;

--
-- Dumping data for table `wpbh_gf_entry_meta`
--

INSERT INTO `wpbh_gf_entry_meta` (`id`, `form_id`, `entry_id`, `meta_key`, `meta_value`) VALUES
(1, 1, 1, '1', 'Carter'),
(2, 1, 1, '2', 'Parsons'),
(3, 1, 1, '3', '(815) 555-3300'),
(4, 1, 1, '4', 'carter@carterparsons.com'),
(5, 1, 1, '5', 'Palm Coast'),
(6, 1, 2, '5', 'Palm Coast'),
(7, 1, 3, '5', 'Palm Coast'),
(8, 1, 4, '5', 'Palm Coast'),
(9, 1, 5, '5', 'Palm Coast'),
(10, 1, 6, '5', 'Venetia Bay');

-- --------------------------------------------------------

--
-- Table structure for table `wpbh_gf_entry_notes`
--

CREATE TABLE `wpbh_gf_entry_notes` (
  `id` int(10) UNSIGNED NOT NULL,
  `entry_id` int(10) UNSIGNED NOT NULL,
  `user_name` varchar(250) COLLATE utf8mb4_unicode_520_ci DEFAULT NULL,
  `user_id` bigint(20) DEFAULT NULL,
  `date_created` datetime NOT NULL,
  `value` longtext COLLATE utf8mb4_unicode_520_ci,
  `note_type` varchar(50) COLLATE utf8mb4_unicode_520_ci DEFAULT NULL,
  `sub_type` varchar(50) COLLATE utf8mb4_unicode_520_ci DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_520_ci;

-- --------------------------------------------------------

--
-- Table structure for table `wpbh_gf_form`
--

CREATE TABLE `wpbh_gf_form` (
  `id` mediumint(8) UNSIGNED NOT NULL,
  `title` varchar(150) COLLATE utf8mb4_unicode_520_ci NOT NULL,
  `date_created` datetime NOT NULL,
  `date_updated` datetime DEFAULT NULL,
  `is_active` tinyint(1) NOT NULL DEFAULT '1',
  `is_trash` tinyint(1) NOT NULL DEFAULT '0'
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_520_ci;

--
-- Dumping data for table `wpbh_gf_form`
--

INSERT INTO `wpbh_gf_form` (`id`, `title`, `date_created`, `date_updated`, `is_active`, `is_trash`) VALUES
(1, 'Contact Us', '2018-10-09 20:12:44', NULL, 1, 0),
(2, 'Contact Us - Enquire', '2018-10-16 14:41:40', NULL, 1, 0);

-- --------------------------------------------------------

--
-- Table structure for table `wpbh_users`
--

CREATE TABLE `wpbh_users` (
  `ID` bigint(20) UNSIGNED NOT NULL,
  `user_login` varchar(60) COLLATE utf8mb4_unicode_ci NOT NULL DEFAULT '',
  `user_pass` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL DEFAULT '',
  `user_nicename` varchar(50) COLLATE utf8mb4_unicode_ci NOT NULL DEFAULT '',
  `user_email` varchar(100) COLLATE utf8mb4_unicode_ci NOT NULL DEFAULT '',
  `user_url` varchar(100) COLLATE utf8mb4_unicode_ci NOT NULL DEFAULT '',
  `user_registered` datetime NOT NULL DEFAULT '0000-00-00 00:00:00',
  `user_activation_key` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL DEFAULT '',
  `user_status` int(11) NOT NULL DEFAULT '0',
  `display_name` varchar(250) COLLATE utf8mb4_unicode_ci NOT NULL DEFAULT ''
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;

--
-- Dumping data for table `wpbh_users`
--

INSERT INTO `wpbh_users` (`ID`, `user_login`, `user_pass`, `user_nicename`, `user_email`, `user_url`, `user_registered`, `user_activation_key`, `user_status`, `display_name`) VALUES
(1, 'carter', '$P$BVkil0p850ufCHs.ovF/0eS96iY/hz1', 'carter', 'carter@carterparsons.com', '', '2018-10-02 19:29:53', '', 0, 'carter');

--
-- Table structure for table `wpbh_options`
--

CREATE TABLE `wpbh_options` (
  `option_id` bigint(20) UNSIGNED NOT NULL,
  `option_name` varchar(191) COLLATE utf8mb4_unicode_ci NOT NULL DEFAULT '',
  `option_value` longtext COLLATE utf8mb4_unicode_ci NOT NULL,
  `autoload` varchar(20) COLLATE utf8mb4_unicode_ci NOT NULL DEFAULT 'yes'
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;

--
-- Dumping data for table `wpbh_options`
--

INSERT INTO `wpbh_options` (`option_id`, `option_name`, `option_value`, `autoload`) VALUES
(1, 'siteurl', 'https://carterparsons.com/dev/tg', 'yes'),
(2, 'home', 'https://carterparsons.com/dev/tg', 'yes'),
(3, 'blogname', 'My Gardens', 'yes'),
(4, 'blogdescription', 'My Gardens', 'yes'),
(5, 'users_can_register', '0', 'yes'),
(6, 'admin_email', 'carter@carterparsons.com', 'yes'),
(7, 'start_of_week', '1', 'yes'),
(8, 'use_balanceTags', '0', 'yes'),
(9, 'use_smilies', '1', 'yes'),
(10, 'require_name_email', '1', 'yes'),
(11, 'comments_notify', '1', 'yes'),
(12, 'posts_per_rss', '10', 'yes'),
(13, 'rss_use_excerpt', '0', 'yes'),
(14, 'mailserver_url', 'mail.example.com', 'yes'),
(15, 'mailserver_login', 'login@example.com', 'yes'),
(16, 'mailserver_pass', 'password', 'yes'),
(17, 'mailserver_port', '110', 'yes'),
(18, 'default_category', '1', 'yes'),
(19, 'default_comment_status', 'open', 'yes'),
(20, 'default_ping_status', 'open', 'yes'),
(21, 'default_pingback_flag', '1', 'yes'),
(22, 'posts_per_page', '10', 'yes'),
(23, 'date_format', 'F j, Y', 'yes'),
(24, 'time_format', 'g:i a', 'yes'),
(25, 'links_updated_date_format', 'F j, Y g:i a', 'yes'),
(26, 'comment_moderation', '0', 'yes'),
(27, 'moderation_notify', '1', 'yes'),
(28, 'permalink_structure', '/blog/%postname%/', 'yes'),
(30, 'hack_file', '0', 'yes'),
(31, 'blog_charset', 'UTF-8', 'yes'),
(32, 'moderation_keys', '', 'no'),
(33, 'active_plugins', 'a:12:{i:0;s:29:\"gravityforms/gravityforms.php\";i:1;s:41:\"Ultimate_VC_Addons/Ultimate_VC_Addons.php\";i:2;s:27:\"autoptimize/autoptimize.php\";i:3;s:31:\"event-tickets/event-tickets.php\";i:4;s:27:\"js_composer/js_composer.php\";i:5;s:23:\"revslider/revslider.php\";i:6;s:37:\"simple-job-board/simple-job-board.php\";i:7;s:43:\"the-events-calendar/the-events-calendar.php\";i:8;s:41:\"wordpress-importer/wordpress-importer.php\";i:9;s:24:\"wordpress-seo/wp-seo.php\";i:10;s:27:\"wp-super-cache/wp-cache.php\";i:11;s:27:\"wps-cleaner/wps-cleaner.php\";}', 'yes'),
(34, 'category_base', '', 'yes'),
(35, 'ping_sites', 'http://rpc.pingomatic.com/', 'yes'),
(36, 'comment_max_links', '2', 'yes'),
(37, 'gmt_offset', '0', 'yes'),
(38, 'default_email_category', '1', 'yes'),
(39, 'recently_edited', '', 'no'),
(40, 'template', 'tuscangardens', 'yes'),
(41, 'stylesheet', 'tuscangardens', 'yes'),
(42, 'comment_whitelist', '1', 'yes'),
(43, 'blacklist_keys', '', 'no'),
(44, 'comment_registration', '0', 'yes'),
(45, 'html_type', 'text/html', 'yes'),
(46, 'use_trackback', '0', 'yes'),
(47, 'default_role', 'subscriber', 'yes'),
(48, 'db_version', '38590', 'yes'),
(49, 'uploads_use_yearmonth_folders', '', 'yes'),
(50, 'upload_path', '', 'yes'),
(51, 'blog_public', '0', 'yes'),
(52, 'default_link_category', '2', 'yes'),
(53, 'show_on_front', 'page', 'yes'),
(54, 'tag_base', '', 'yes'),
(55, 'show_avatars', '1', 'yes'),
(56, 'avatar_rating', 'G', 'yes'),
(57, 'upload_url_path', '', 'yes'),
(58, 'thumbnail_size_w', '150', 'yes'),
(59, 'thumbnail_size_h', '150', 'yes'),
(60, 'thumbnail_crop', '1', 'yes'),
(61, 'medium_size_w', '300', 'yes'),
(62, 'medium_size_h', '300', 'yes'),
(63, 'avatar_default', 'mystery', 'yes'),
(64, 'large_size_w', '1024', 'yes'),
(65, 'large_size_h', '1024', 'yes'),
(66, 'image_default_link_type', '', 'yes'),
(67, 'image_default_size', '', 'yes'),
(68, 'image_default_align', '', 'yes'),
(69, 'close_comments_for_old_posts', '0', 'yes'),
(70, 'close_comments_days_old', '14', 'yes'),
(71, 'thread_comments', '1', 'yes'),
(72, 'thread_comments_depth', '5', 'yes'),
(73, 'page_comments', '0', 'yes'),
(74, 'comments_per_page', '50', 'yes'),
(75, 'default_comments_page', 'newest', 'yes'),
(76, 'comment_order', 'asc', 'yes'),
(77, 'sticky_posts', 'a:0:{}', 'yes'),
(78, 'widget_categories', 'a:2:{i:2;a:4:{s:5:\"title\";s:0:\"\";s:5:\"count\";i:0;s:12:\"hierarchical\";i:0;s:8:\"dropdown\";i:0;}s:12:\"_multiwidget\";i:1;}', 'yes'),
(79, 'widget_text', 'a:2:{i:1;a:0:{}s:12:\"_multiwidget\";i:1;}', 'yes'),
(80, 'widget_rss', 'a:2:{i:1;a:0:{}s:12:\"_multiwidget\";i:1;}', 'yes'),
(81, 'uninstall_plugins', 'a:3:{s:27:\"wp-super-cache/wp-cache.php\";s:22:\"wpsupercache_uninstall\";s:27:\"autoptimize/autoptimize.php\";s:29:\"autoptimizeMain::on_uninstall\";s:27:\"LayerSlider/layerslider.php\";s:29:\"layerslider_uninstall_scripts\";}', 'no'),
(82, 'timezone_string', '', 'yes'),
(83, 'page_for_posts', '0', 'yes'),
(84, 'page_on_front', '52', 'yes'),
(85, 'default_post_format', '0', 'yes'),
(86, 'link_manager_enabled', '0', 'yes'),
(87, 'finished_splitting_shared_terms', '1', 'yes'),
(88, 'site_icon', '0', 'yes'),
(89, 'medium_large_size_w', '768', 'yes'),
(90, 'medium_large_size_h', '0', 'yes'),
(91, 'wp_page_for_privacy_policy', '3', 'yes'),
(92, 'show_comments_cookies_opt_in', '0', 'yes'),
(93, 'initial_db_version', '38590', 'yes');
```

---
### Cracking 5 (Hard)
Our analysts have obtained password dumps storing hacker passwords. We know many of them enjoy traveling, maybe their passwords reflect that.

| User | Password Ciphertext | Answer |
| :---: | :---: | :---: |
| Joe | $1$xmc$8eQm4viYGtSPR4tP44l8T0 | germany2310 |
| Eve | $1$dac$19.Se2mouHmPmGa.Vv7EO/ | 19canada |
| Daniel | $1$erj$JgjXnThWvnEKYBZJY1CP./ |  |
| Kristy | $1$axu$351SxqKtW7CgjWvVAzuca1 |  |

---
### Cracking 5 (Hard)
Our analysts have obtained password dumps storing hacker passwords, they all seem to be the same theme. Can you figure them out?

| User | Password Ciphertext | Answer |
| :---: | :---: | :---: |
| Ade | 6d1289cb7b791e9ef6d0b90c72de27b2 | friends3 |
| Elliot | 85786db03c596a76a79019c5dda1ee79 | theoffice23 |
| Eve | edbe626bc5c8f4ead357b1edb5f09e80 | |
| Patrick | b8157dc3216fe2ca07c3ce3efa8b7b17 | |
| Rachel | 8d90c6034d207d210d77f62a5f4fcbb1 | |
