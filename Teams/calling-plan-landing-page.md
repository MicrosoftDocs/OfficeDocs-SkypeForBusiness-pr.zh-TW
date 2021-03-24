---
title: Microsoft Teams 中的通話方案
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
f1.keywords:
- NOCSH
ms.reviewer: crowe
search.appverid: MET150
description: 決定哪一個 Microsoft Phone 系統通話方案最適合在 Teams 中的雲端語音上為貴組織服務。
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: b88af706f79dd195e2f9363ff45e586a1123686f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102729"
---
# <a name="which-calling-plan-is-right-for-you"></a>哪一個通話方案適合您？ 

您已完成開始使用[。](get-started-with-teams-quick-start.md) 您已使用[聊天、團隊、頻道和應用程式](deploy-chat-teams-channels-microsoft-teams-landing-page.md)在組織中推出 Teams。 您可能已經部署會議 [&會議](deploy-meetings-microsoft-teams-landing-page.md)。 現在，您已準備好新增雲端語音工作負載，而且您決定使用 Microsoft Phone System 與通話方案，以連接到公用交換電話網絡 (PSTN) 。 

本文將說明通話方案的核心部署決策，以及您可能要根據貴組織的需求設定的其他考慮。 您也應該閱讀 [Microsoft Teams 中的雲端語音](cloud-voice-landing-page.md) ，以瞭解更多關於 Microsoft 雲端語音產品的資訊。


## <a name="learn-more-about-calling-plans"></a>深入瞭解通話方案

下列文章提供有關部署及使用 Microsoft 通話方案之詳細資訊：

- [Microsoft 365 或 Office 365 中的電話系統](what-is-phone-system-in-office-365.md)
- [Microsoft 365 或 Office 365 的通話方案](calling-plans-for-office-365.md)
- [設定通話方案](set-up-calling-plans.md)


## <a name="core-deployment-decisions"></a>核心部署決策

若要使用 Microsoft 做為電話電信業者，您必須取得通話方案授權，並將授權指派給電話系統使用者。 

有兩種類型的通話方案可用：

- 國內通話方案 
- 國內和國際通話方案

|問問自己|動作 |
|------------|-------|
|我的地區是否提供通話方案？ 哪些使用者位置會提供通話方案服務？ | 詳細資訊，請參閱音訊會議與通話方案的國家 [/地區可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)。 | 
我的使用者是否需要國際電話？ | 詳細資訊，請參閱 [Microsoft 365 或 Office 365 的通話方案](calling-plans-for-office-365.md)。 |
我的使用者是否擁有通話方案授權？ | 若要購買及指派授權，請參閱 [步驟 2：購買及指派授權](set-up-calling-plans.md#step-2-buy-and-assign-licenses)。 |
我的使用者是否都有直接撥入 (號碼) 電話號碼？ | 若要取得電話號碼，請參閱 [步驟 3：取得電話號碼](set-up-calling-plans.md#step-3-get-phone-numbers)。 |
|||

### <a name="transfer-phone-numbers-to-microsoft-365-or-office-365"></a>將電話號碼轉接至 Microsoft 365 或 Office 365

您可輕鬆將目前服務提供者的電話號碼移轉至 Teams。 將電話號碼移植到 Teams 之後，Microsoft 會成為您的服務提供者，並且會針對這些電話號碼向您計費。 詳細資訊，請參閱將 [電話號碼轉接至 Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)。


### <a name="phone-numbers-and-emergency-locations"></a>電話號碼和緊急位置

使用 Microsoft 365 或 Office 365 中的通話方案，貴組織的每個使用者必須擁有唯一的直撥 (DID) 電話號碼和對應的已驗證緊急位址。 您也可以在緊急位址內指定緊急 (例如辦公室號碼或樓面號碼) 。 

|問問自己|動作 |
|:------------|:-------|
|我想要緊急位址和位置資訊的詳細資料如何？ |詳細資訊，請參閱 [什麼是緊急位置、位址和通話路由？](/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing)。


### <a name="calling-identity"></a>通話身分識別

根據預設，所有外發通話會使用指派的電話號碼做為通話身分識別 (來電) 。 來電接收者可以快速識別來電者，並决定是否接聽或拒絕接聽來電。

|問問自己|動作 |
|:------------|:-------|
|我要遮罩或停用本機號碼嗎？ | 若要變更或封鎖本機號碼，請參閱[設定使用者的本機號碼。](set-the-caller-id-for-a-user.md) |
|||