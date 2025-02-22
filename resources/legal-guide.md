---
description: >-
  The information below is not legal advice. This is general legal information
  intended as a resource.
---

# Legal Guide

{% hint style="info" %}
**The information provided in this document is based on the guidance provided by** [**0x** ](https://www.0x.org/)**in their** [**0x Legal Guide**](https://docs.0x.org/developer-resources/0x-legal-guide)**.**
{% endhint %}

## Introduction

Due to the diverse nature of projects that can be built in crypto, there are no uniform legal standards applicable to all projects. However, there are certain legal regimes that are more likely to impact such projects. This document surveys some of the relevant laws and regulations that developers should be aware of and potentially seek qualified and individualized legal advice on to ensure compliance.&#x20;

_The information below is not legal advice. This is general legal information intended as a resource for the ecosystem. To understand how this information may impact your project specifically, hire a good lawyer._&#x20;

How all of the laws intersect with the exchange of digital assets is still an evolving issue and demands careful consideration. For additional resources, check out the Legal Library below that contains links to important cases, statements from regulators, and other legal commentary specific to the digital asset industry.

## United States

### Federal Securities Regulation

The United States has a set of intricate laws and regulations that apply to activities involving financial instruments that meet the legal definition of a security. These laws cover a wide range of topics, such as the rules around selling securities, who can own specific types of securities, and the required disclosures for securities investors. Due to the complexity of these laws, it's crucial to determine which transactions involving crypto assets fall under the category of securities. Answering this question is a critical first step for anyone working with crypto assets in the US.

#### What is a Security

So what is a security? Unfortunately, as even [federal courts have recognized](https://scholar.google.com/scholar_case?case=10900624885862830401\&q=gary+plastic\&hl=en\&as_sdt=6,47#p238), the definition of a security is "broad and ambiguous." Consequently, it is difficult to layout a bright line rule by which a security can easily be distinguished from a non-security. Instead, [courts have designed a flexible test](https://scholar.google.com/scholar_case?case=12975052269830471754) that is intended to "to meet the countless and variable schemes devised by those who seek the use of money of others on the promise of profits."

In particular, the U.S. Supreme Court has outlined a four-part test for determining whether a transaction qualifies as a form of a security called an “investment contract." Originally set forth in [SEC v. W.J. Howey Co.](https://scholar.google.com/scholar_case?case=12975052269830471754\&q=sec+v+howey\&hl=en\&as_sdt=6,47#p298), the Court has explained that a transaction is an “investment contract” when it involves (1) an investment of money (2) in a common enterprise (3) with an expectation of profit (4) to be derived from the efforts of others.

There is a long history of cases interpreting whether various financial instruments meet this definition of a security, covering everything from [bank certificates of deposits](https://scholar.google.com/scholar_case?case=10900624885862830401) to interests in [whiskey barrels](https://scholar.google.com/scholar_case?case=14457626249500273939). Some of the most influential cases have been compiled [here](broken-reference). However, there are many more cases analyzing various elements of the Howey test, each hinging on the specific facts of the particular transaction.

As proof of the inherent difficulty in defining a clear border between what is and is not a security, there have been numerous instances of courts applying the Howey test to seemingly similar transactions and coming to different results. For example, there are several cases holding certain [real estate leases](https://scholar.google.com/scholar_case?case=4030348895733612487) to be securities when offered in a particular manner. Likewise, there are numerous cases addressing when the sale of a tangible product like [the sale of beavers](https://scholar.google.com/scholar_case?case=8958675023427121133) may be offered as part of a securities transaction. These cases demonstrate that courts place less of a premium on the nature of the underlying product being sold and more on the manner in which it was sold.

#### Application to the crypto asset industry

It is important to understand that the primary way the law develops in the U.S. is through the application of existing legal precedent by courts to cases that present new fact patterns not previously contemplated. As of early 2019, very few U.S. courts have wrestled with how to apply the Howey test to crypto asset transactions, so it is still unclear how certain lines will be drawn to delineate securities from non-securities. There are a handful of cases pending in front of courts that may result in decisions that directly address this issue, and inevitably there will be future cases so long as certain teams use the sale of crypto assets as a way to promise future profits to third parties. For now, though, most agree that there is a lack of clarity for developers building projects in this industry.

Moreover, there is significant confusion even among lawyers as to how Howey should apply in the context of secondary market transactions in which the original token issuer is not directly involved. Even if an initial sale of a token had some of the hallmarks of a securities offering, it is unclear whether a subsequent transaction by a token holder to, for example, trade the token for a cryptokitty is somehow also a securities transaction. This confusion stems in part from the fact that virtually every historical case applying Howey deals with a transaction in which a promoter is promising some form of financial return to the counterparty.

In the context of this unclear regulatory environment, creators are left to make good faith attempts at trying to comply with the securities law. Some helpful factors to consider include:

* How was the initial token sale or distribution conducted, including what did the development team represent to prospective tokens purchasers?
* How is the token designed to operate within the network being created, including whether the design is meant to confer specific financial returns to the token holder or instead be used in some consumptive manner?
* What is the current status of development on the underlying network or project, and is their interest and involvement from those other than the team that issued the tokens?

This suggested framework is not meant to be comprehensive, and depending on the nature of the project being developed, it may be helpful to work directly with lawyers to design a process that provides adequate protection.

#### The SEC's current position

The Securities and Exchange Commission (SEC), the primary regulator of the securities market in the US, has been active in voicing its opinion about certain activities in the crypto asset industry. The SEC's first major foray in the industry came in July 2017 in the form of [a report](https://www.sec.gov/litigation/investreport/34-81207.pdf) stating that sale of tokens by "The DAO" constituted the sale of securities. The SEC has since reached settlements with several industry participants and also issued several statements about when certain activity within the industry may be subject to securities regulations. A complete listing of those documents can be found [here](broken-reference). Notably, some members of the SEC have said that they believe that the vast majority of tokens sold as part of a fundraising effort (so called "ICOs") were securities offerings.

In March 2019, the SEC's Strategic Hub for Innovation and Financial Technology (aka FinHub) issued a framework intended to help those within the crypto asset industry evaluate which assets may be viewed by the Staff of the SEC as securities. The [FinHub framework](https://www.sec.gov/corpfin/framework-investment-contract-analysis-digital-assets) identifies numerous factors to consider when analyzing whether the sale of a crypto asset meets the final two prongs of the Howey test, i.e., whether there is an expectation of profit based on the efforts of a third party. The framework places a strong emphasis on factors used to determine whether an "Active Participant" exists that provides "essential managerial efforts that effect the success of the enterprise, and investors reasonably expect to derive profits from those efforts."

Currently, one of the largest areas of debate relating to the SEC's position on the crypto asset industry is how it plans to apply securities law to the secondary market trading of tokens that may have initially been sold as part of a securities offering. The SEC's own Director of Corporate Finance has opined that "strictly speaking, the token – or coin or whatever the digital information packet is called – all by itself is not a security." Instead, the Director appropriately noted that "a careful and fact-sensitive legal analysis" of secondary market trading is necessary, focused on how the token is offered and sold, including the reasonable expectations of purchasers. The Director offered one standard for determining when a token is not a security based on whether the network upon which a token exists is "sufficiently decentralized." In a [speech proposing this standard](https://www.sec.gov/news/speech/speech-hinman-061418), the Director also laid out several factors that could be considered to determine whether a token is "sufficiently decentralized." The more-recent FinHub framework also addresses this issue but does not use the term "sufficiently decentralized." Instead, the framework lays out several factors to be analyzed around whether the value of the asset is still dependent on the efforts of the "Active Participants" and to what extent the underlying network technology is fully functional.

The primary takeaway from these statements is that the SEC has recognized that a crypto asset previously sold in a securities offering can later be sold on the secondary market in a non-securities transactions under certain circumstances. However, there are still many questions to be answered about the standard the SEC will use to distinguish between securities and non-securities transactions of crypto assets. Furthermore, despite advocating for a nuanced analysis of each token's network to make such a determination, the SEC has not actively engaged with this concept in the enforcement actions it has brought against certain industry participants. Instead, the SEC has issued orders in settled cases involving secondary market participants in which it has alleged without further explanation that the tokens themselves are the securities. Therefore, it is unclear exactly what analysis is currently actually being applied as it relates to secondary market transactions of crypto assets.

There has been significant debate about the SEC's general position relative to the crypto asset industry. Many have called on the SEC to provide greater clarity to the industry and to avoid regulating by enforcement. Most notably, for the first time ever, a crypto project in the SEC's crosshairs has decided not to settle and instead litigate against the SEC in court. The SEC filed [a complaint in federal court](https://www.sec.gov/litigation/complaints/2019/comp-pr2019-87.pdf) that alleges that Kik Interactive conducted an unregistered securities offering when it sold Kin tokens for approximately $100 million dollars in other assets. [Kik's submission to the SEC](http://kinecosystem.org/wells_response.pdf) arguing that it should not be sued was released to the public, and together these two documents present the stark difference in opinion that some within in the industry have aboue the SEC's current approach to crypto assets.

The Kik case will play out in court and could potentially result in judicial decisions that provide further clarity as to how securities law will apply. However, there have also been [efforts](https://coincenter.org/entry/principles-for-clarifying-sec-jurisdiction-over-cryptocurrencies-and-icos) outside the judicial realm, and even [some early legislative bills](https://www.cnbc.com/2018/12/20/lawmakers-look-to-change-secs-72-year-old-securities-definition-to-exclude-cryptocurrencies.html) in Congress, calling for the creation of standards defining the line between securities and non-securities more clearly.

_Important sidenote: All statements from the SEC, such as the speeches cited in this section as well as all SEC orders that result from settlements with alleged wrongdoers, do not constitute binding law and should generally be interpreted as merely reflecting the position of the SEC. To what extent courts applying the law will agree or disagree with the SEC's positions remains to be seen._

#### What is an Exchange?

Most of the securities law discussion in the industry to date has focused on the threshold question of what is a security. This makes sense because there is no need to look at other aspects of the securities laws if a transaction does not involve a security. But so long as the question of which crypto assets may be securities remains unclear, it is also important to consider a few of these other areas of securities law.

One area of focus should be what constitutes a securities exchange. A securities exchange is defined as "any organization, association, or group of persons that: (1) brings together the orders of multiple buyers and sellers; and (2) uses established non-discretionary methods (whether by providing a trading facility or by setting rules) under which such orders interact with each other, and the buyers and sellers entering such orders agree to the terms of the trade." Any platform meeting the definition of a securities exchange generally must register with the SEC and follow a number of restrictive rules.

The [current rule adopted by the SEC](https://www.govinfo.gov/content/pkg/FR-1998-12-22/html/98-33299.htm) relating to exchanges was modernized in 1998 in response to market participants incorporating technology that the existing "regulatory framework, designed more than six decades ago, did not envision." Obviously, the pace of technological development has only increased since 1998, and some of the concepts set forth in the SEC's formal interpretation of the rule are difficult to apply, particularly to concepts presented by blockchain technologies.

In November 2018, the SEC [settled an action](https://www.sec.gov/litigation/admin/2018/34-84553.pdf) with the founder of a trading platform called EtherDelta on the basis that the platform was an unregistered securities exchange. In its settlement order, the SEC alleged that some of the 500 tokens listed on EtherDelta were securities although it did not identify which ones. The SEC then alleged that EtherDelta operated as an exchange because:

> "EtherDelta brought together orders by receiving and storing orders in tokens in the EtherDelta order book and displaying the top 500 orders (including token symbol, size, and price) as bids and offers on the EtherDelta website. EtherDelta provided the means for these orders to interact and execute through the combined use of the EtherDelta website, order book, and pre-programmed trading protocols defined in the EtherDelta smart contract. These established non-discretionary methods allowed Users to agree upon the terms of their trades in tokens on EtherDelta during the Relevant Period."

As explained above, settlement orders like this are not binding law. Moreover, every case is fact-dependent such that this order cannot answer how the SEC would view marketplaces where the various functions operate differently, are distributed among different parties, or where all tokens are not indiscriminately offered to users. However, this provides the first practical insight into which issues the SEC is focusing on when analyzing trading platforms and should be closely considered by any trading platform.

### Federal Commodities and Derivatives Regulation

When we think about commodities, historically this term has been used to refer to agriculture products like wheat, corn and sugar. However, U.S. law has evolved to define a commodity extremely broadly to also include "all services, rights, and interests . . . in which contracts for future delivery are presently or in the future dealt in.” As a result, almost anything (except [onions](https://en.wikipedia.org/wiki/Onion_Futures_Act)) can constitute a “commodity” under the definition.

The Commodities Futures Trading Commission (CFTC) is the primary regulator of "commodities interests". The [CFTC has taken the position](https://www.cftc.gov/sites/default/files/idc/groups/public/@lrenforcementactions/documents/legalpleading/enfcoinfliprorder09172015.pdf) that some virtual currencies like Bitcoin are commodities, and there have already been [court cases that agree](https://scholar.google.com/scholar_case?case=16464466787559233193) with this position. Based on the broad definition discussed above, it is possible that virtually every crypto asset can be legally defined as a commodity. From a practical perspective, it seems that the CFTC is taking a deliberate approach to the crypto asset industry, and is not actively extending its jurisdiction where, for example, the SEC may first want to identify an asset as a security. Moreover, it remains to be seen whether the CFTC will identify some limit to the definition of a commodity for assets like non-fungible tokens and crypto collectibles.

Commodities are regulated very differently than securities. Indeed, just because something is a commodity does not mean that it is subject to specific rules such as the requirements around securities governing who can purchase them, how they must be offered, etc. This is due to the fact that, historically, the spot market for trading commodities has been considerably smaller than the market for trading derivatives of commodities. Most people do not trade actual stalks of corn for cash. Instead, most people trade contracts based on the future price of corn (or other commodities) - i.e., futures contracts. However, with crypto assets, much of the exchange activity occurs in the spot market.

There are no laws directly regulating spot market transactions for commodities (i.e., transactions that involve the full payment of the purchase price and contemporaneous delivery of commodity at the time the transaction is entered by the parties). The CFTC has limited authority to police the spot markets for fraud and manipulation, but cannot adopt rules that directly control how spot market participants transact.

U.S. law does set forth detailed restrictions for a wide range of non-spot market transactions, including those involving commodities derivatives, future delivery or financing, leverage, or margin. As a result, the CFTC has been actively regulating nascent futures markets in commodities like Bitcoin. Additionally, the CFTC has been monitoring smart contract applications closely and [has put out statements](https://www.cftc.gov/sites/default/files/2018-11/LabCFTC_PrimerSmartContracts112718_0.pdf) explaining that certain actors must comply with applicable regulations when using smart contracts to facilitate regulated transactions in commodities interests, such as forwards, futures, options and swaps.

At a high level, a CFTC-regulated transaction can only be conducted over regulated exchanges, which include, depending on the type of transaction, Designated Contract Markets (“DCMs”) and Swap Execution Facilities (“SEFs”). Exceptions to this requirement may apply, but broadly speaking, these exceptions are only available to certain sophisticated market participants or high-net-worth individuals. In addition, the CFTC directly regulates the intermediaries that facilitate CFTC-regulated transactions, including introducing brokers, futures commission merchants, swap dealers, commodity pool operators, or commodity trading advisors. The application process to become a DCM, SEF, or regulated intermediary is costly and difficult, and regulated exchanges and intermediaries are subject to extensive ongoing regulatory oversight by the CFTC.

### OFAC Sanctions

The U.S. Department of Treasury's Office of Foreign Assets Control (OFAC) maintains a list of people that U.S. persons are not permitted to transact with in any manner. The list can generally be broken down into two categories: 1) People from specific [embargoed countries and geogpraphic areas](https://www.treasury.gov/resource-center/sanctions/Programs/Pages/Programs.aspx) such as Iran, North Korea, and Syria; and 2) people on the [Specially Designated Nationals (SDN) list](https://www.treasury.gov/resource-center/sanctions/SDN-List/Pages/default.aspx), which is comprised of select individuals responsible for particularly bad behavior like human trafficking or government corruption.

Unlike most other U.S. financial laws that establish process-based rules that must be followed, OFAC sanctions simply prohibits certain activity - i.e., doing business with people on the sanctions list. Relatedly, sanctions laws impose strict liability, meaning there is no legal defense for someone who tried to do the right thing. That being said, historically, the consequences for those who purposefully evade or ignore sanctions laws are much more severe than for those who attempt to avoid transacting with a sanctioned person. Indeed, consequences can be as severe as criminal prosecution and jail time.

In practice, most companies implement risk-based processes custom tailored to their business in order to avoid sanctions violations. The convenience store in Michigan faces virtually no risk of conducting significant business with sanctioned individuals and thus likely does not need a "know your customer" (KYC) program. On the other hand, a U.S. affiliated bank operating in countries that rank high in corruption will likely need to be able to conduct thorough background checks on customers to ensure compliance.

OFAC sanctions is one of the legal regimes that does not suffer from a significant lack of clarity when applied to most crypto asset projects. For any U.S. person operating such a project, they are potentially liable if a sanctioned individual uses their service. For more information, OFAC has included some [frequently asked questions about virtual currencies on its website](https://www.treasury.gov/resource-center/faqs/Sanctions/Pages/faq_compliance.aspx#vc_faqs). Notably, OFAC states that it may identify certain virtual currency wallet addresses belonging to individuals on the SDN list so that U.S. persons can block transactions with that address. The first instance of this practice occured in November 2018, 2h3n OFAC [identified](https://home.treasury.gov/news/press-releases/sm556) bitcoin wallet addresses belonging to two individuals added to the SDN list.

The extent of the risk of exposure to sanctioned individuals and countries can vary widely based on the specific project, and may be influenced by such variables as the type of assets being offered, the volume of transactions being facilitated, the areas in which the service is available. Ultimately, there is no one-size-fits-all to OFAC sanctions compliance but it is an issue that each project should consider.

### Federal Anti-Money Laundering Regulation

U.S. law requires certain intermediaries in the financial system to assist in detecting and preventing money laundering activity and terrorist financing. Specifically, the Bank Secrecy Act (BSA) requires certain “financial institutions” to assist the U.S. government by, for example, implementing risk-based anti-money laundering (AML) programs and filing reports with the government when suspicious transactions are identified by those programs.

The types of financial institutions covered by the BSA range broadly and include everything from banks to casinos. Importantly, for developers working with crypto assets, the BSA applies to “money services businesses,” a category that is further subdivided to include “money transmitters.” The Financial Crimes Enforcement Network (FinCEN), which is the primary federal regulator responsible for enforcing the BSA, has interpreted certain businesses involved in crypto assets to fall under the definition of money transmitters such that they must comply with the BSA.

So what is a money transmitter? A money transmitter is defined as anyone involved as a business in “the acceptance of currency, funds, or other value that substitutes for currency from one person and the transmission . . .to another location or person by any means.” When adopting this language, FinCEN confirmed that the reference to “other value that substitutes for currency” was intended to capture informal value systems that do not involve the transfer of fiat currency. The BSA regulations make the determination of whether someone is a money transmitter explicitly based on the specific “facts and circumstances,” which is a signal in the legal world that the definition is meant to be broad and flexible.

In 2013, FinCEN [issued guidance](https://www.fincen.gov/sites/default/files/shared/FIN-2013-G001.pdf) directed in part at the crypto asset industry delineating when FinCEN considered certain crypto businesses to be money transmitters. Specifically, FinCEN differentiated between three categories of people involved with so-called "convertible virtual currencies". As a preliminary matter, FinCEN defines convertible virtual currency as a "medium of exchange" that "either has an equivalent value in real currency, or acts as a substitute for real currency."

It should be evident from this broad definition that most of the current tokens widely available on the market likely meet this definition, particularly most ERC-20 tokens. However, we can also look to the other end of the spectrum and see how a non-fungible token in the form of a cryptocollectible may not meet this definition as it is hard to imagine how we could use something like cryptokitties as a medium of exchange despite each potentially having some discoverable value in fiat.

Where the line is between what is and is not a convertible virtual currency is not well defined yet. There have only been a few court cases addressing which tokens meet the definition of a convertible virtual currency. A handful of cases have confirmed that bitcoin is a convertible virtual currency. Separately, Ripple settled a case brought by the government that was premised on XRP being a convertible virtual currency. But with respect to the ever-increasing number of tokens available on the market, the only source of guidance is the language of the definition and statements by FinCEN that indicate that they interpret the term broadly to cover many tokens.

For now, let's assume we are dealing with a token that meets the definition of a convertible virtual currency. The guidance describes certain activities involving convertible virtual currencies that constitute money transmission. Specifically, FinCEN created the following categories:

* User - A user is defined as someone who obtains convertible virtual currency in order to purchase goods or services. In subsequent statements from FinCEN, this definition has been broadened somewhat to include someone who purchases convertible virtual currency as investment for his or her own account.
* Exchanger - An exchanger is defined as someone engaged in the business of exchanging virtual currency for real currency, funds, or another virtual currency by either 1) accepting and transmitting a convertible virtual currency or 2) buying and selling a convertible virtual currency for any reason.
* Administrator - An administrator is defined as someone engaged as a business in issuing (putting into circulation) a virtual currency, and who has the authority to redeem (to withdraw from circulation) such virtual currency. As most crypto assets are issued without an ability to mandate redemption, this definition is generally not that relevant for our purposes.

Since issuing its initial guidance in 2013, FinCEN has clarified these definitions in subsequent "Administrative Rulings." In [one of these administrative rulings](https://www.fincen.gov/sites/default/files/shared/FIN-2014-R001.pdf), FinCEN clarified that a person who exchanges virtual currency for their own account as not as a business service to third parties is considered a user and not an exchanger. In [another ruling](https://www.fincen.gov/sites/default/files/shared/FIN-2014-R002.pdf), FinCEN stated "\[t]he production and distribution of software, in and of itself, does not constitute acceptance and transmission of value, even if the purpose of the software is to facilitate the sale of virtual currency. "

There is a strong argument that the definition of exchanger does not apply to someone who does not take custody of another person's virtual currency. As explained thoughtfully in [this report](https://coincenter.org/files/2017-05/report-bsa-crypto-token1.pdf) from Coin Center:

_"A non-custodial exchange is probably not an exchanger or a money transmitter. If, like Craigslist or any other online classified advertising service, the business merely helps individual buyers and sellers find and communicate with each other, then it is never “accepting and transmitting” tokens or bitcoins for its users, nor is it “buying or selling” tokens or bitcoins. It may be commonly understood as an exchange because it deals in exchange-related information (e.g. order-books, offers, acceptances, communications between buyers and sellers) but it, as a company, is never doing the actual currency conversion or handling the actual tokens or money; that all happens peer-to-peer. Another way to characterize what these companies do is: development of a web-based software tool (e.g. a website) that facilitates peer-to-peer exchange. As we discussed earlier, FinCEN’s Software and Investment Ruling describes mere software development and distribution as outside the scope of BSA regulation."_

The facts and circumstances of any particular project may impact this analysis. As with this entire primer, the above is just intended as a legal resource and for actual legal advice on any particular project or situation, you should hire a lawyer.

## Legal Library

### Federal Securities Regulation

#### Key Cases

_Regarding Crypto Assets_

* [SEC v. Blockvest, LLC](https://www.sec.gov/litigation/litreleases/2019/order24400.pdf) (S.D. Cal. 2019)

_Important Howey Test Cases_

* [SEC v. C.M. Joiner Leasing Corp.](https://scholar.google.com/scholar_case?case=11822356269281048781), 320 U.S. 344 (1943)
* [SEC v. W.J. Howey Co.](https://scholar.google.com/scholar_case?case=12975052269830471754), 328 U.S. 293 (1946)
* [Tcherepnin v. Knight](https://scholar.google.com/scholar_case?case=5481496770318090573), 389 U.S. 332 (1967)
* [United Housing Foundation, Inc. v. Forman](https://scholar.google.com/scholar_case?case=11168754825085710379), 421 U.S. 837 (1975)
* [Glen-Arden Commodities, Inc. v. Costantino](https://scholar.google.com/scholar_case?case=14457626249500273939), 493 F.2d 1027 (2d Cir. 1974)
* [Gary Plastic Packaging Corp. v. Merrill Lynch](https://scholar.google.com/scholar_case?case=10900624885862830401), 756 F.2d 230 (2d Cir. 1985)

#### SEC Statements & Settlement Orders

* [Framework for Investment Contract Analysis of Digital Assets](https://www.sec.gov/corpfin/framework-investment-contract-analysis-digital-assets)
  * Proposed framework from SEC's FinHub as to how to analyze whether the sale or offering of a digital asset constitutes a security in the form of an investment contract.
* [SEC Settlement Order re: Gladius Network LLC](https://www.sec.gov/litigation/admin/2019/33-10608.pdf) (Feb. 20, 2019)
  * Settlement for unregistered securities offering resulting in no penalty due to self disclosure and cooperation.
* [Speech by Commissioner Hester Peirce: Regulation: A View from Inside the Machine](https://www.sec.gov/news/speech/peirce-regulation-view-inside-machine) (Feb. 8, 2019)
* [Statement on Digital Asset Securities Issuance and Trading](https://www.sec.gov/news/public-statement/digital-asset-securites-issuuance-and-trading) (Nov. 16, 2018)
  * Statement from multiple SEC divisions highlighting recent enforcement actions and providing some guidance on the SEC's interpretation about the intersection of securities law and token offerings and trading.
* [SEC Settlement Order re: AirFox](https://www.sec.gov/litigation/admin/2018/33-10575.pdf) (Nov. 16, 2018)
  * Settlement based on allegations that AirFox token sale constituted an unregistered securities offering and that AirFox tokens are securities.
* [SEC Settlement Order re: Paragon](https://www.sec.gov/litigation/admin/2018/33-10574.pdf) (Nov. 16, 2018)
  * Settlement based on allegations that Paragon token sale constituted an unregistered securities offering and that PRG tokens are securities.
* [SEC Settlement Order re: Zachary Coburn](https://www.sec.gov/litigation/admin/2018/34-84553.pdf) (Nov. 8, 2018)
  * Settlement based on allegation that EtherDelta operated as a securities exchange without proper registration.
* [SEC Settlement Order re: TokenLot](https://www.sec.gov/litigation/admin/2018/33-10543.pdf) (Sept. 11, 2018)
  * Settlement based on allegations that TokenLot operated as an unregistered broker-dealer by soliciting investors to participate in ICOs and facilitating secondary market trading of tokens that were securities.
* [Digital Asset Transactions: When Howey Met Gary (Plastic)](https://www.sec.gov/news/speech/speech-hinman-061418): William Hinman - SEC Director of Division of Corporate Finance (June 14, 2018)
  * Speech by SEC official opining that ETH in its current form is not a security and laying out factors fow when a sufficiently decentralized digital asset may not be a security.
* [Statement on Potentially Unlawful Online Platforms for Trading Digital Assets](https://www.sec.gov/news/public-statement/enforcement-tm-statement-potentially-unlawful-online-platforms-trading) (Mar. 7, 2018)
  * Statement from multiple SEC divisions regarding regulatory issues and consumer risks related to trading tokens on exchanges, particularly tokens that meet the definition of a security.
* [SEC Settlement Order re: Munchee](https://www.sec.gov/litigation/admin/2017/33-10445.pdf) (Dec. 11, 2017)
  * Settlement based on allegation that MUN token sale constituted sale of unregistered securities.
* [Statement on Cryptocurrencies and Initial Coin Offerings](https://www.sec.gov/news/public-statement/statement-clayton-2017-12-11) (Dec. 11, 2017)
  * Statement from SEC Chairman directed at investors and industry participants regarding potential regulatory issues with ICOs.
* [Report of Investigation Pursuant to Section 21(a) of the Securities Exchange Act of 1934: The DAO](https://www.sec.gov/litigation/investreport/34-81207.pdf) (July 25, 2017)
  * Report alleging that DAO token sale constituted sale of unregistered securities and that DAO tokens were securities.
* Other SEC resources:
  * [Initial Coin Offerings](https://www.sec.gov/spotlight-initial-coin-offerings-and-digital-assets) resource page
  * [Index of statements](https://www.sec.gov/spotlight-initial-coin-offerings-and-digital-assets) re ICOs and digital assets
  * [SEC FinHub](https://www.sec.gov/finhub) landing page

#### Commentary & Analysis

* [Electronic Frontier Foundation letter to the SEC re: EtherDelta settlement](https://www.eff.org/files/2019/02/12/correspondence_from_eff_re_in_the_matter_of_zachary_coburn_file_no._3-18888-2.pdf) (Feb. 12, 2019)
* [Submission by Kik Interactive Inc. to the SEC](http://kinecosystem.org/wells_response.pdf) (Dec. 10, 2018)
* [What Are Token Securities? Some Questions from the Perplexed](https://corpgov.law.harvard.edu/2018/12/20/when-are-tokens-securities-some-questions-from-the-perplexed/) by James J. Park - UCLA School of Law (Dec. 20, 2018)
* [What can the EtherDelta settlement tell us about how decentralized exchanges are regulated?](https://coincenter.org/entry/what-can-the-etherdelta-settlement-tell-us-about-how-decentralized-exchanges-are-regulated) by Peter Van Valkenburgh - Coin Center (Nov. 8, 2018)
* [Securities Law & Crypto - Unqualified Opinions #14](https://messari.substack.com/p/securities-law-and-crypto-unqualified) by Katherine Wu - Messari (Oct. 11, 2018)
* [Securities Regulations and Initial Coin Offerings: A Legal Primer](https://fas.org/sgp/crs/misc/R45301.pdf) by Jay B. Sykes - Congressional Research Service (Aug. 31, 2018)
* [Framework for Securities Regulation of Cryptocurrencies (v2)](https://coincenter.org/files/securities-cryptocurrency-framework-v2.1.pdf) by Peter Van Valkenburgh - Coin Center (Aug. 10, 2018)
* [Principles for Clarifying SEC Jurisdiction over Cryptocurrencies and ICOs](https://coincenter.org/entry/principles-for-clarifying-sec-jurisdiction-over-cryptocurrencies-and-icos) by Peter Van Valkenburgh - Coin Center (May 24, 2018)
* [Regulation of Token Sales](https://youtu.be/tz8t5OTc7R0) {video} - Coin Center (Oct. 24, 2017)

### Federal Commodities & Derivatives Regulation

#### Key Cases

* [CFTC v. My Big Coin Pay, Inc.](https://www.cftc.gov/sites/default/files/2018-10/enfmybigcoinpayincmemorandum092618_0.pdf) (D. Mass. 2018)
* [CFTC v. McDonnell](https://scholar.google.com/scholar_case?case=16464466787559233193), 287 F.Supp.3d 213 (E.D.N.Y. 2018)

#### CFTC Statements & Settlement Orders

* [How the CFTC can take a pro-innovation posture while maintaining orderly markets](https://coincenter.org/entry/how-the-cftc-can-take-a-pro-innovation-posture-while-maintaining-orderly-markets) - Article by Commissioner Brian Quintenz (Feb. 12, 2019)
* [Remarks of Commissioner Brian Quintenz at the 38th Annual GITEX Technology Week Conference](https://www.cftc.gov/PressRoom/SpeechesTestimony/opaquintenz16) regarding smart contract regulation (Oct. 16, 2018)
* Proposed Interpretation on Virtual Currency “Actual Delivery” in Retail Transactions
  * [CFTC announcement](https://www.cftc.gov/PressRoom/PressReleases/7664-17) (Dec. 15, 2017)
  * [Proposed interpretation](https://www.cftc.gov/sites/default/files/idc/groups/public/@lrfederalregister/documents/file/2017-27421a.pdf)
* [Primer on Smart Contracts](https://www.cftc.gov/sites/default/files/2018-11/LabCFTC_PrimerSmartContracts112718_0.pdf) (Nov. 27, 2018)
* [Backgrounder on Oversight of and Approach to Virtual Currency Markets](https://www.cftc.gov/sites/default/files/idc/groups/public/%40customerprotection/documents/file/backgrounder_virtualcurrency01.pdf) (Jan. 4, 2018)
* [Primer on Virtual Currencies](https://www.cftc.gov/sites/default/files/idc/groups/public/%40customerprotection/documents/file/labcftc_primercurrencies100417.pdf) (Oct. 17, 2017)
* [CFTC Settlement Order re: Bitfinex](https://www.cftc.gov/sites/default/files/idc/groups/public/@lrenforcementactions/documents/legalpleading/enfbfxnaorder060216.pdf) (June 2, 2016)
* [CFTC Settlement Order re: Coinflip](https://www.cftc.gov/sites/default/files/idc/groups/public/@lrenforcementactions/documents/legalpleading/enfcoinfliprorder09172015.pdf) (Sept. 17, 2015)

#### Commentary & Analysis

* Cryptocurrency Derivatives, Funds and Advisers: Key Considerations Under U.S. Commodity Laws by Andrew P. Cross - Perkins Coie (Four-Part Series: [1](https://www.derivativesandreporeport.com/2018/09/cryptocurrency-derivatives-funds-and-advisers-key-considerations-under-u-s-commodity-laws-part-1-cryptos-are-commodites-except-when-they-are-not/), [2](https://www.derivativesandreporeport.com/2018/09/cryptocurrency-derivatives-funds-and-advisers-key-considerations-under-u-s-commodity-laws-part-2-the-regulation-of-commodities-quite-substantial-even-if-not-substantive/), [3](https://www.derivativesandreporeport.com/2018/10/cryptocurrency-derivatives-funds-and-advisers-key-considerations-under-u-s-commodity-laws-part-3-why-commodity-interests-are-of-interest/), [4](https://www.derivativesandreporeport.com/2018/10/cryptocurrency-derivatives-funds-and-advisers-key-considerations-under-u-s-commodity-laws-part-4-about-the-interests-of-interest/))
* [Frequently Asked Questions on Virtual Currency and CFTC Jurisdiction](https://www.skadden.com/insights/publications/2017/11/faqs-on-virtual-currency-and-cftc-jurisdiction) by several attorneys at Skadden, Arps, Slate, Meagher & Flom LLP (Nov. 15, 2017)
* [Bitcoin and Virtual Currencies: Welcome to Your Regulators](https://www.bakermckenzie.com/en/-/media/files/people/kluchenek-matthew/ar_na_mkluchenek_bitcoinvirtualcurrency_2016.pdf) by Matthew Kluchenek - Baker & McKenzie LLP

### OFAC Sanctions

#### OFAC Statements

* [FAQ on Virtual Currencies](https://www.treasury.gov/resource-center/faqs/Sanctions/Pages/faq_compliance.aspx#vc_faqs)
* Addition of two Individuals to SDN List and identification of associated bitcoin public addresses
  * [Treasury Dept. PR Release](https://home.treasury.gov/news/press-releases/sm556) (Nov. 28, 2018)
  * [SDN Designation](https://www.treasury.gov/resource-center/sanctions/OFAC-Enforcement/Pages/20181128.aspx) (Nov. 28, 2018)

#### Commentary & Analysis

* [What is OFAC and how does it apply to Bitcoin?](https://coincenter.org/entry/what-is-ofac-and-how-does-it-apply-to-bitcoin) by Joshua Garcia (May 3, 2015)

### Federal Anti-Money Laundering Regulation

#### Key Cases

* DOJ and FinCEN actions against BTC-E
  * [FinCEN Assessment of Civil Money Penalty](https://www.fincen.gov/sites/default/files/enforcement_action/2017-07-26/Assessment%20for%20BTCeVinnik%20FINAL%20SignDate%2007.26.17.pdf) (July 26, 2017)
  * [Indictment of BTC-E and Alexander Vinnik](https://www.justice.gov/usao-ndca/press-release/file/984661/download) (Jan. 17, 2017)
* [US v. Murgio](https://scholar.google.com/scholar_case?case=14324236322418966686), 209 F.Supp.3d 698 (S.D.N.Y. 2016)
* DOJ and FinCEN settlements with Ripple Labs (May 5, 2015)
  * [DOJ Non-Prosecution Agreement and Statement of Facts](https://www.justice.gov/sites/default/files/opa/press-releases/attachments/2015/05/05/settlement_agreement.pdf)
  * [FinCEN Assessment of Civil Money Penalty](https://www.fincen.gov/sites/default/files/shared/Ripple_Assessment.pdf)
* [US v. Faiella](https://scholar.google.com/scholar_case?case=11943246728627907201), 39 F.Supp.3d 544 (S.D.N.Y. 2014)

#### Statements & Administrative Rulings

* [Application of FinCEN’s Regulations to Certain Business Models Involving Convertible Virtual Currencies](https://www.fincen.gov/sites/default/files/2019-05/FinCEN%20CVC%20Guidance%20FINAL.pdf) (May 9, 2019)
  * Comprehensive guidance from FinCEN on the application of the Bank Secrecy Act to various crypto asset business models, including those involved in decentralized exchange.
* [Prepared Remarks of FinCEN Director Kenneth A. Blanco](https://www.fincen.gov/news/speeches/prepared-remarks-fincen-director-kenneth-blanco-delivered-2018-chicago-kent-block) (Aug. 9, 2018)
  * Speech summarizing FinCEN's approach to virtual currency.
* [Department of Treasury Letter to Senator Ron Wyden](https://coincenter.org/files/2018-03/fincen-ico-letter-march-2018-coin-center.pdf) (Feb. 13, 2018)
* FinCEN Administrative Rulings
  * [Application of FinCEN’s Regulations to a Virtual Currency Trading Platform](https://www.fincen.gov/sites/default/files/administrative_ruling/FIN-2014-R011.pdf) (Oct. 29, 2014)
    * Traditional centralized exchange model involving matching buyers and sellers directly constitutes money transmission despite argument that the exchange does not sit in the middle of a transaction.
  * [Application of FinCEN’s Regulations to a Virtual Currency Payment System](https://www.fincen.gov/sites/default/files/administrative_ruling/FIN-2014-R012.pdf) (Oct. 27, 2014)
    * Company that exchanges virtual currency for fiat in order to facilitate payment for vendors interested in accepting virtual currency is a money transmitter.
  * [Application of Money Services Business regulations to the rental of computer systems for mining virtual currency](https://www.fincen.gov/sites/default/files/administrative_ruling/FIN-2014-R007.pdf) (Apr. 29, 2014)
    * Rental of computer system for third party to mine virtual currency does not constitute money transmission when all virtual currency goes directly to third party's wallet and no virtual currency is exchanged
  * [Application of FinCEN’s Regulations to Virtual Currency Software Development and Certain Investment Activity](https://www.fincen.gov/sites/default/files/shared/FIN-2014-R002.pdf) (Jan. 30, 2014)
    * (1) The production and distribution of software alone is not sufficient to constitute money transmission and (2) buying and selling virtual currencies solely for one's own account is not money transmission.
  * [Application of FinCEN’s Regulations to Virtual Currency Mining Operations](https://www.fincen.gov/sites/default/files/shared/FIN-2014-R001.pdf) (Jan. 30, 2014)
    * A bitcoin miner is not a money transmitter when converting bitcoin to fiat for its own purposes and not as a business service for the benefit of others.
* [Application of FinCEN's Regulations to Persons Administering, Exchanging, or Using Virtual Currencies](https://www.fincen.gov/sites/default/files/shared/FIN-2013-G001.pdf) (Mar. 18, 2013)
  * Initial guidance from FinCEN addressing who within the virtual currency industry is considered a money transmitter.

#### Commentary & Analysis

* [Electronic Cash, Decentralized Exchange, and the Constitution](https://coincenter.org/files/e-cash-dex-constitution.pdf) by Peter Van Valkenburgh - Coin Center (March 2019)
* [The Bank Secrecy Act, Cryptocurrencies and New Tokens: What is Known and What Remains Ambiguous](https://coincenter.org/files/2017-05/report-bsa-crypto-token1.pdf) by Peter Van Valkenburgh - Coin Center (May 2017)

{% hint style="info" %}
**The information provided in this document is based on the guidance provided by** [**0x** ](https://www.0x.org/)**in their** [**0x Legal Guide**](https://docs.0x.org/developer-resources/0x-legal-guide)**.**
{% endhint %}
