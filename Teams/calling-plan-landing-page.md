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
description: 決定哪一個 Microsoft 電話系統通話方案最適合在 Teams 的雲端語音上為貴組織服務。
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: e11c6f6cbb53808ba259afd90420ac9855c9731d
ms.sourcegitcommit: d87991ed2d3e4d70edb048378763a17ff689b710
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/07/2022
ms.locfileid: "66682472"
---
# <a name="which-calling-plan-is-right-for-you"></a>哪一個通話方案適合您？

您已完成 [開始使用](get-started-with-teams-quick-start.md)。 您已使用[聊天、團隊、頻道和應用程式](deploy-chat-teams-channels-microsoft-teams-landing-page.md)在組織中推出 Teams。 您可能已部署 [會議&會議](deploy-meetings-microsoft-teams-landing-page.md)。 現在您已準備好新增雲端語音工作負載，並且決定搭配通話方案使用 Microsoft 電話系統連線到公用交換電話網路 (PSTN) 。

本文將說明通話方案的核心部署決策，以及您可能想要根據組織需求設定的其他考慮。 您也應該閱讀 [Microsoft Teams 中的雲端語音](cloud-voice-landing-page.md) ，以取得 Microsoft 雲端語音服務的詳細資訊。

## <a name="learn-more-about-calling-plans"></a>深入瞭解通話方案

下列文章提供部署和使用 Microsoft 通話方案的詳細資訊：

- [Microsoft 365 或 Office 365 中的電話系統](what-is-phone-system-in-office-365.md)
- [Microsoft 365 或 Office 365 通話方案](calling-plans-for-office-365.md)
- [設定通話方案](set-up-calling-plans.md)

## <a name="core-deployment-decisions"></a>核心部署決策

若要使用 Microsoft 做為電話語音電信業者，您必須取得通話方案授權，並將授權指派給您的電話系統使用者。

有兩種類型的通話方案可用：

- 國內通話方案
- 國際通話方案

|問問自己|動作 |
|------------|-------|
|我的區域是否提供通話方案？ 哪些使用者位置將提供通話方案服務？ | 如需詳細資訊，請參閱 [音訊會議和通話方案的國家/地區可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)。 |
我的使用者需要國際電話嗎？ | 如需詳細資訊，請參閱[Microsoft 365 或 Office 365 通話方案](calling-plans-for-office-365.md)。 |
我的使用者是否擁有通話方案授權？ | 若要購買及指派授權，請參閱 [步驟 2：購買並指派授權](set-up-calling-plans.md#step-2-buy-and-assign-licenses)。 |
我的每個使用者是否有直接向內撥號 (是否) 電話號碼？ | 若要取得電話號碼，請參閱 [步驟 3：取得電話號碼](set-up-calling-plans.md#step-3-get-phone-numbers)。 |
|||

### <a name="transfer-phone-numbers-to-microsoft-365-or-office-365"></a>將電話號碼移轉到 Microsoft 365 或 Office 365

您可以輕鬆地將電話號碼從目前的服務提供者移轉到 Teams。 將電話號碼移轉到 Teams 之後，Microsoft 將會成為您的服務提供者，並會向您收取這些電話號碼。 如需詳細資訊，請參閱 [將電話號碼移轉到 Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)。

### <a name="phone-numbers-and-emergency-locations"></a>電話號碼和緊急位置

使用 Microsoft 365 或 Office 365 中的通話方案，貴組織中的每個使用者都必須有唯一的直接向內撥號 (DID) 電話號碼以及對應的已驗證緊急位址。 您也可以在緊急位址內指定緊急位置 (例如辦公室號碼或樓面) 。

|問問自己|動作 |
|:------------|:-------|
|我想要緊急位址和位置資訊的詳細程度為何？ |如需詳細資訊，請參閱 [什麼是緊急位置、位址和通話路由？](/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing)。

### <a name="calling-identity"></a>通話身分識別

根據預設，所有撥出電話都會使用指派的電話號碼作為通話身分識別 (來電者識別碼) 。 來電接收者可以快速識別來電者，並决定是否接聽或拒絕接聽來電。

|問問自己|動作 |
|:------------|:-------|
|我是否想要遮罩或停用來電者識別碼？ | 若要變更或封鎖來電者識別碼，請參閱 [設定使用者的來電識別碼](set-the-caller-id-for-a-user.md)。 |
|||
