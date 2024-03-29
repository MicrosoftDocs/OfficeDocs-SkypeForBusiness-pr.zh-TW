---
title: Microsoft 365 中的音訊會議
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: conceptual
ms.assetid: a5a696c3-d321-4e61-9aad-e3a87041196e
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
search.appverid: MET150
audience: admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- ms.teamsadmincenter.audioconferencing.overview
- seo-marvel-apr2020
description: 瞭解 Microsoft 365 中的音訊會議如何讓使用者從他們的電話撥入會議。
ms.openlocfilehash: 1ac2842d219648c5a5deef0d687698cd7b5544dd
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/10/2022
ms.locfileid: "67641924"
---
# <a name="audio-conferencing-in-microsoft-365"></a>Microsoft 365 中的音訊會議

Microsoft 365 中的音訊會議可讓使用者從手機撥入會議。 音訊會議可讓最多 1000 位手機出席者參加。

## <a name="what-is-audio-conferencing"></a>什麼是音訊會議？

 (撥入會議) 電話對出門在外且無法使用膝上型電腦或行動裝置上的 Microsoft Teams 應用程式出席會議的使用者非常有用。 但在其他情況下，使用電話參加 Teams 會議會比在電腦上使用應用程式更好：
  
- 當網際網路連線能力受限制時。
- 當會議只有音訊時。
- 該人員嘗試加入 Teams 會議，但會議失敗。
- 撥入的通話品質更好時。
- 與會者可以使用藍牙裝置以「免持」方式加入會議。
- 與會者會發現這對他們而言更為簡單且方便。

您只需要為計劃排程或主持會議的人員設定音訊會議即可。 撥入的會議出席者不需獲得任何指派的授權或進行其他設定。

出席者加入會議後，他們也可以撥出電話並邀請其他來電者加入 Teams 會議。
如需詳細資訊，請參閱 [從 Teams 會議撥出，讓其他人可以加入會議](dialing-out-from-a-teams-meeting-so-other-people-can-join-it.md) 。

## <a name="what-does-it-cost"></a>需要多少費用？

如需定價資訊，請參閱[音訊會議的定價](https://go.microsoft.com/fwlink/?linkid=799762&clcid=0x409)。

## <a name="where-is-it-available"></a>可以在哪裡取得？

利用音訊會議，您的使用者可以使用付費和免付費電話號碼撥入會議。 組織若已啟用音訊會議功能，系統便會自動將付費 (服務) 電話號碼當作共用的音訊會議號碼來指派給組織。 您也可以將其他城市的專用付費和免付費電話號碼指派給貴組織。

提供免付費電話號碼 (服務號碼)，但僅在部分國家/地區提供。 若要查看您的國家或地區可使用的項目，請參閱[音訊會議與通話方案的適用國家/地區](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)。

當您決定要為組織部署音訊會議之後，就必須為組織中負責排程/主持音訊會議的每位人員購買一份 **音訊會議** 授權。

## <a name="how-do-conferencing-bridges-work"></a>會議橋接器如何運作？

當您設定 Teams 的音訊會議時，您會獲得音訊會議橋接器。 一個會議橋接器可以包含一或多個電話號碼。 您設定的電話號碼會包含在 Teams 應用程式的會議邀請中。 您可以[變更您的會議橋接器上的電話號碼](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)，也可以[變更其他音訊會議橋接器設定](change-the-settings-for-an-audio-conferencing-bridge.md)。

音訊會議橋接器可接聽電話使用手機撥入會議人員的電話。 它會透過自動語音應答的語音提示回應呼叫者，然後根據您的設定，可以播放通知並要求呼叫者記錄他們的名稱。 **Microsoft 橋接器設定** 可讓您變更會議通知和會議加入體驗的設定，並設定會議召集人在 [Microsoft Teams 中](set-the-pin-length-for-audio-conferencing-meetings-in-teams.md)使用的 PIN 長度。 如果會議召集人無法使用 Teams 應用程式加入會議，請使用 PIN 來開始會議。

## <a name="dial-in-phone-numbers-set-on-an-audio-conferencing-bridge"></a>音訊會議橋接器上設定的撥入電話號碼

可指派給您的會議橋接器的音訊會議電話號碼有兩個類型：**共用** 和 **專用**。 任何呼叫者都可以使用這兩個類型的號碼來加入組織中正在進行的音訊會議。
  
 **專用電話號碼** 是只有在組織內部使用者才可以使用的電話號碼。 您可以變更某人撥入其中一個號碼時所使用的語言。 您必須取得這些語言的服務電話號碼。
  
 **共用電話號碼** 是可與其他 Microsoft 365 共用的電話號碼。 您無法變更某人撥入其中一個號碼時所使用的語言。
  
雖然指派給召集人的預設音訊會議號碼只會包含在會議邀請中，呼叫者可以使用指派給您的會議橋接器的任何電話號碼加入會議。 您可以使用每個會議邀請中包含的 [尋找當地電話號碼] 連結，來取得可用來加入會議的電話號碼清單。

如需詳細資訊，請參閱 [Microsoft Teams 中音訊會議的電話號碼](phone-numbers-for-audio-conferencing-in-teams.md) 。

## <a name="automatically-assigned-audio-conferencing-phone-numbers"></a>自動指派的音訊會議電話號碼

組織若已啟用音訊會議功能，系統便會自動將共用的音訊會議電話號碼指派給組織。 指派電話號碼時，系統會將電話號碼指派為會議橋接器的預設電話號碼。 指派為橋接器預設號碼的電話號碼，將會是來自組織的國家/地區的電話號碼。

> [!NOTE]
> 登入 **Microsoft 365 系統管理中心**，並查看 [組織設定檔] 下，即可找出組織的國家或地區位置。

> [!CAUTION]
> 由於委內瑞拉、印尼和阿拉伯聯合大公國 (UAE) 的付費電話號碼有限，來自這些國家/地區中的組織，將不會自動獲指派音訊會議付費電話號碼。 來自這些位置的免付費電話號碼是否可供使用，視可用庫存而定。

若要查看已自動指派電話號碼給組織之國家/地區的清單，請參閱[音訊會議與通話方案的適用國家/地區](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)。

## <a name="how-do-you-get-dedicated-phone-numbers"></a>如何取得專用電話號碼？

專用音訊會議電話號碼是您可以取得並接著指派給組織的服務號碼。 您可以透過下列三個方式之一，為您的會議橋接器取得專用的付費和免付費電話號碼：

- **使用 Teams 系統管理中心。** 對於某些國家/地區，您可以使用 Teams 系統管理中心取得會議橋的號碼。 請參閱[取得服務電話號碼](./getting-service-phone-numbers.md)。

- **轉移現有的號碼。** 您可以將現有號碼從目前的服務提供者或電信業者移轉至 Microsoft 365。 如需詳細資訊，請參閱[將電話號碼轉接至 Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) 或[管理貴組織的電話號碼](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)，協助您完成此作業。  
  
- **使用表單要求新號碼。** 有時候 (視您的國家/地區而定) 您將無法使用 Teams 系統管理中心取得新的電話號碼，或者您需要特定的電話號碼或區碼。 若是如此，您將需要下載表單並將它傳回給我們。 如需詳細資訊，請參閱[管理貴組織的電話號碼](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。

## <a name="how-do-you-set-it-up"></a>如何設定？

在您決定為使用者設定音訊會議之後，請參閱 [設定 Microsoft Teams 的音訊會議](set-up-audio-conferencing-in-teams.md) ，瞭解您必須遵循的步驟。

## <a name="related-topics"></a>相關主題

[Microsoft Teams 音訊會議的電話號碼](phone-numbers-for-audio-conferencing-in-teams.md)
