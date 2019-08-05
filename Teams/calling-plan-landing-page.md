---
title: Microsoft 團隊中的通話方案
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
ms.reviewer: crowe
search.appverid: MET150
description: '[通話方案] 登陸頁面'
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9b9d1a012c545dbaf8f8c65d87f58718bda13946
ms.sourcegitcommit: bf7de2101862a154eb375c06bc89e6e0c4872119
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/22/2019
ms.locfileid: "36183549"
---
# <a name="which-calling-plan-is-right-for-you"></a>哪一種通話方案最適合您？ 

您已完成[快速入門](get-started-with-teams-quick-start.md)。 您已在整個組織中利用[聊天、團隊、頻道、& 應用程式](deploy-chat-teams-channels-microsoft-teams-landing-page.md)來推出小組。 也許您已將[會議 & 會議](deploy-meetings-microsoft-teams-landing-page.md)已部署。 現在您已經準備好要新增雲端語音工作負載, 而您決定使用 Microsoft 手機系統搭配通話方案來連線至公用的交換電話網絡 (PSTN)。 

本文說明通話方案的核心部署決定, 以及您可能想要根據貴組織的需求設定的其他考慮。 您也應該閱讀[Microsoft 團隊中的雲端語音](cloud-voice-landing-page.md), 以取得關於 Microsoft 雲端語音服務的詳細資訊。


## <a name="learn-more-about-calling-plans"></a>深入瞭解通話方案

下列文章提供有關部署和使用 Microsoft 通話方案的詳細資訊:

- [Office 365 中的電話系統](what-is-phone-system-in-office-365.md)
- [Office 365 的通話方案](calling-plans-for-office-365.md)
- [設定通話方案](set-up-calling-plans.md)


## <a name="core-deployment-decisions"></a>核心部署決定

若要使用 Microsoft 作為您的電話語音運營商, 您必須取得通話方案授權, 並將其指派給您的電話系統使用者。 

提供兩種通話方案類型:

- 國內通話方案 
- 國內和國際通話方案

|問自己|執行 |
|------------|-------|
|我的區域是否提供通話方案？ 哪些使用者位置將會有通話計畫服務？ | 如需詳細資訊, 請參閱[音訊會議與通話方案的國家/地區可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)。 | 
我的使用者需要國際通話嗎？ | 如需詳細資訊, 請參閱[Office 365 的通話方案](calling-plans-for-office-365.md)。 |
我的使用者是否有通話方案授權？ | 若要購買並指派授權, 請參閱[步驟 2: 購買並指派授權](set-up-calling-plans.md#step-2-buy-and-assign-licenses)。 |
我的使用者每個都有直向撥打電話號碼嗎？ | 若要取得電話號碼, 請參閱[步驟 3: 取得電話號碼](set-up-calling-plans.md#step-3-get-phone-numbers)。 |
|||

### <a name="transfer-phone-numbers-to-office-365"></a>將電話號碼傳送至 Office 365

您可以輕鬆地將您的電話號碼從目前的服務提供者轉接至團隊。 在您將電話號碼移植至團隊後, Microsoft 就會成為您的服務提供者, 並將您的電話號碼帳單。 如需詳細資訊, 請參閱[將電話號碼轉移至 Office 365](transfer-phone-numbers-to-office-365.md)。


### <a name="phone-numbers-and-emergency-locations"></a>電話號碼和緊急位置

使用 Office 365 中的通話方案, 貴組織中的每位使用者都必須有一個唯一的直接撥出電話號碼, 以及對應的驗證緊急位址。 您也可以在緊急位址內指定緊急地點 (例如, 辦公室號碼或底價編號)。 

|問自己|執行 |
|:------------|:-------|
|我要如何詳細說明緊急位址和位置資訊？ |如需詳細資訊, 請參閱[什麼是緊急位置、位址及呼叫路由？](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing)。


### <a name="calling-identity"></a>通話身分識別

根據預設, 所有出站通話都會將指派的電話號碼做為呼叫身分識別 (來電者識別碼)。 通話的收件者可以快速識別來電者, 決定是否要接受或拒絕通話。

|問自己|執行 |
|:------------|:-------|
|我想要遮罩或停用本機號碼嗎？ | 若要變更或封鎖本機號碼, 請參閱[設定使用者的本機號碼](set-the-caller-id-for-a-user.md)。 |
|||




