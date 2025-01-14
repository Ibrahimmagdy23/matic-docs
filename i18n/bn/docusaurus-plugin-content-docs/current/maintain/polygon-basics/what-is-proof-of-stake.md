---
id: what-is-proof-of-stake
title: প্রুফ অফ স্ট্যাক কী?
description: স্টেক কনসেনসাস মেকানিজমের প্রমাণ কি Learn Learn
keywords:
  - docs
  - matic
  - polygon
  - stake
  - delegate
  - validate
  - pos
image: https://wiki.polygon.technology/img/polygon-wiki.png
---

# প্রুফ অফ স্ট্যাক কী? {#what-is-proof-of-stake}

প্রুফ অফ স্ট্যাক (PoS) হচ্ছে পাবলিক ব্লকচেইনের কনসেনসাস অ্যালগরিদমের একটি বিভাগ যা নেটওয়ার্কে যাচাইকারীদের আর্থিক [স্ট্যাকের](/docs/maintain/glossary.md#staking) উপর নির্ভরশীল।

কাজের প্রমাণ (PoW) পাবলিক ব্লকচেইনে, অ্যালগরিদম যেসব অংশগ্রহণকারী লেনদেন যাচাই এবং নতুন ব্লক তৈরি করতে ক্রিপ্টোগ্রাফিক পাজল সমাধান করেন তাদের পুরস্কার প্রদান করা হয়। PoW ব্লকচেইন উদাহরণ: বিটকয়েন, Ethereum (মিশে যাওয়ার আগে)।

PoS ভিত্তিক পাবলিক ব্লকচেইনে কয়েকজন যাচাইকারীদের একটি দল মিলে পরবর্তী ব্লকের প্রস্তাব করে এবং তাতে ভোট প্রদান করেন। প্রতিটি যাচাইকারীর ভোটের মান তাদের ডিপোজিটের পরিমাণ — [স্ট্যাকের](/docs/maintain/glossary.md#staking) উপর নির্ভরশীল। PoS সিস্টেমের অন্যতম বড় সুবিধাগুলি হচ্ছে বেশি নিরাপদ, সেন্ট্রালাইজেশনের ঝুঁকি কম এবং কম বিদ্যুৎ খরচ হয়। PoS blockchain উদাহরণ: Ethereum 2.0, Polygon।

সাধারণত, PoS অ্যালগরিদম নিচে বর্ণিত উপায়ে কাজ করে থাকে। ব্লকচেইনে যাচাইকারী একটি সেট এবং যে কেউ ব্লকচেইনের বেস cryptocurrency (Ethereum-এর ক্ষেত্রে, ETH) ধারণ করে তা হবে একটি যাচাইকারী হতে পারে একটি বিশেষ ধরনের লেনদেনের পাঠে, যা একটি ডিপোজিটে তাদের ETH লক করে। নতুন ব্লক তৈরি এবং তাতে সম্মত হওয়ার প্রক্রিয়াটি তারপর কনসেনসাস অ্যালগরিদমের মাধ্যমে সম্পন্ন করা হয় যেখানে সকল বিদ্যমান যাচাইকারী অংশগ্রহণ করতে পারবেন।

ক্রিপ্টো জগতে অনেক ধরনের কনসেনসাস অ্যালগরিদম রয়েছে এবং কনসেনসাস অ্যালগরিদমে অংশগ্রহণ করা যাচাইকারীদের পুরস্কার প্রদানের অনেক উপায় রয়েছে। তাই, ক্রিপ্টো জগতে বিভিন্ন "ধরনের" প্রুফ অফ স্ট্যাকও পাওয়া যায়। একটি অ্যালগরিদমিক দৃষ্টিকোণ থেকে, দুটি প্রধান ধরনের আছে: chain-based PoS এবং [BFT-style PoS](https://en.wikipedia.org/wiki/Byzantine_fault_tolerance)।

**চেইন-ভিত্তিক প্রুফ** অফ স্ট্যাকে, অ্যালগরিদমটি প্রতিটি সময়ের স্লটে (যেমন, ১০ সেকেন্ডের প্রতিটি সময়কাল একটি সময়ের স্লট হিসেবে গণ্য হতে পারে) অর্ধ-র‍্যান্ডম ভাবে একজন যাচাইকারী নির্বাচন করে এবং সেই যাচাইকারীকে একটি একক ব্লক নির্মাণের অধিকার প্রধান করে, তবে এই ব্লকটিকে অবশ্যই পূর্ববর্তী কোনো ব্লকের (সাধারণত পূর্ববর্তী দীর্ঘতম ব্লকের শেষের ব্লকটির) সাথে সম্পর্কিত হতে হবে এবং এইভাবে বেশিরভাগই ব্লকই আস্তে আস্তে একক ক্রমবর্ধমান চেইনে রূপান্তরিত হয়ে যায়।

**BFT-style Proof of Stake** এ যাচাইকারী **এলোমেলোভাবে** ব্লক **প্রস্তাব** করার অধিকার দি. ে নি. ে। যার উপর একটি ব্লক **ক্যানোনিকাল** করা হয় একটি multi-round প্রসেসের মাধ্যমে যেখানে প্রতিটি যাচাইকারী প্রতিটি রাউন্ডের সময় কিছু নির্দিষ্ট ব্লকের জন্য **একটি ভোট** পাঠা, , এবং প্রক্রিয়ার শেষে, সকল (সৎ এবং অনলাইন) যাচাইকারী স্থায়ীভাবে সম্মত হন যে কোন প্রদত্ত ব্লক চেইনের অংশ। মনে রাখবেন যে ব্লকটি এখনও **একসাথে চেইনও** হতে পারে। মূল পার্থক্য is ে একটি ব্লকের উপর ঐক্যমত, একটি ব্লকের মধ্যে আসতে পারে এবং পরে চেইনের দৈর্ঘ্য বা আকারের উপর নির্ভর করে না।

আরও বিস্তারিত জানার জন্য, [https://github.com/ethereum/wiki/wiki/Proof-of-Stake-FAQ](https://github.com/ethereum/wiki/wiki/Proof-of-Stake-FAQ) পড়ুন।

## এছাড়াও দেখুন {#see-also}

* [ডেলিগেটর](/docs/maintain/glossary.md#delegator)
* [যাচাইকারী](/docs/maintain/glossary.md#validator)
