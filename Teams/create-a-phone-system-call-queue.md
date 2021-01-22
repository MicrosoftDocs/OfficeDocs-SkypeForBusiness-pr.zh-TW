---
title: 在 Microsoft Teams 中建立通話佇列
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview"
- Phone System
- seo-marvel-apr2020
description: 瞭解如何使用 Microsoft Teams 為通話佇列設定電話系統，提供問候語、等候音樂、重新導向通話及其他功能。
ms.openlocfilehash: d696b37f95d06c529aa330bd77e2ec91e1ffc9ad
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2021
ms.locfileid: "49919023"
---
# <a name="create-a-call-queue"></a>建立通話佇列

通話佇列提供將來電者路由給組織中可協助解決特定問題之人員的方法。 通話會一次分配一個給佇列 (代理程式 *人員) 。* 

通話佇列提供：

- 問候語訊息。

- 當人員正在等候佇列時播放音樂。

- 呼叫路由 - *在 First In， First Out (* FIFO) - 到代理程式。

- 佇列溢出和超時的處理選項。

按照本文中的程式操作之前，請務必先閱讀[Teams](plan-auto-attendant-call-queue.md)自動撥打和通話[](plan-auto-attendant-call-queue.md#getting-started)佇列的規劃，並遵循入門步驟。

若要設定通話佇列，請在 Teams 系統管理中心展開[語音，按一下通話 **佇列**，然後按一下 [**新增**。

## <a name="resource-account-and-language"></a>資源帳戶及語言

![資源帳戶和語言設定螢幕擷取畫面](media/call-queue-name-language.png)

1. 輸入通話佇列的名稱。 當代理人收到來自佇列的來電時，會看到此名稱。

2. 按一下 **[新增** 帳戶，搜尋要用於此通話佇列的資源帳戶;按一下 [新增，然後按一下 **新增。**

3. 選擇語言。 如果您啟用系統產生的語音提示和語音信箱抄 (，就會使用這個) 。

## <a name="greetings-and-music-on-hold-in-queue"></a>佇列中保留的問候語和音樂

指定是否要在來電者到達佇列時播放問候語。 您必須上傳包含要播放之問候語的 MP3、WAV 或 WMA 檔案。

當來電者排入佇列時，Teams 會提供預設音樂給來電者。 如果您想要播放特定的音訊檔案，請選擇播放音訊檔案，然後上傳 MP3、WAV 或 WMA 檔案。

> [!NOTE]
> 上傳的錄製不能大於 5 MB。
> Teams 通話佇列提供的預設音樂可免收貴組織應付的任何權利金。 

## <a name="call-agents"></a>通話代理程式

請參閱先決條件 [，](plan-auto-attendant-call-queue.md#prerequisites) 以將代理人新增到通話佇列。

![通話佇列的使用者和群組設定螢幕擷取畫面](media/call-queue-users-groups.png)

您可以透過群組個別新增最多 20 個代理程式，以及最多 200 個代理程式。

若要將使用者新增到佇列，請按一下[新增使用者，搜尋使用者，按一下 [**新增**，然後按一下新增 **。**

若要將群組新增到佇列，請按一下 [**新增** 群組;搜尋群組;按一下[新增，然後按一下 [**新增**。 您可以使用通訊群組清單、安全性群組，以及 Microsoft 365 群組或 Microsoft Teams 團隊。

> [!NOTE]
> 新加入群組的新使用者最多可能需要八小時的時間，才能到達第一個通話。

## <a name="call-routing"></a>通話路由

![會議模式和路由方法設定螢幕擷取畫面](media/call-queue-conference-mode-routing-method.png)

**在代理人** 接受通話後，會議模式可大幅縮短來電者與代理人聯繫的時間。 若要讓會議模式運作，通話佇列中的代理人必須使用下列其中一個用戶端：

  - 最新版本的 Microsoft Teams 桌面用戶端、Android App 或 iOS 應用程式
  - Microsoft Teams 手機版本 1449/1.0.94.2020051601 或更新版本
  
代理人的 Teams 帳戶必須設定為 Teams-only 模式。 不符合需求的代理人不會包含在通話路由清單中。 如果您的代理人都使用相容的用戶端，建議您為通話佇列啟用會議模式。

> [!NOTE]
> 會議模式不支援忙碌中。 若未啟用目前狀態式路由，非通話佇列通話的代理程式仍可能會顯示通話佇列通話。

**路由方法** 會決定代理程式從佇列接收呼叫的順序。 請從這些選項中選擇：

- **Attendant 路由** 會同時呼叫佇列的所有代理程式。 第一位接電話的代理人會接到來電。

- **串連路由** 會以通話代理程式清單中指定的順序，一個接一個撥打 **給所有通話** 代理程式。 如果代理人拒絕或不接電話，來電會撥打給下一位代理人，並嘗試所有代理人，直到來電接回或停止通話。

- **圓形平衡** 呼叫的路由，讓每個通話代理程式從佇列獲得相同數目的通話。 這是在內入銷售環境中確保所有通話代理人均能有相等機會的做法。

- **最長閒置** 時間路由每個通話給閒置時間最長之代理人。 如果代理人的目前狀態為線上，或者其目前狀態已離開少於 10 分鐘，則視為閒置中。 目前狀態超過 10 分鐘的代理程式視為閒置中，且除非其目前狀態變更為線上，才能接聽來電。 

![路由、退出宣告及警示時間設定的螢幕擷取畫面](media/call-queue-presence-agents-time.png)


**目前狀態式路由** 會使用通話代理程式的可用性狀態，來判斷所選路由方法的通話路由清單中是否應該包含代理人。 其顯示狀態設定為可用的通話代理程式會包含在通話路由清單中，而且可以接聽來電。 其可用性狀態設定為任何其他狀態的代理人會排除在通話路由清單中，而且不會接聽來電，直到其顯示狀態變更回可用 **。** 

您可以使用任何路由方法啟用目前狀態式通話路由。

如果代理人選擇不接聽來電，無論其顯示狀態設定為何種狀態，他們將不會包含在通話路由清單中。 

> [!NOTE]
> 啟用目前狀態式路由時，使用商務用 Skype 用戶端的代理人不會包含在通話路由清單中。 如果您有使用商務用 Skype 的代理人，請勿啟用目前狀態通話路由。

**代理人警示** 時間會指定代理人的電話在佇列將來電重新導向到下一個代理人前會響鈴多久。

針對大量佇列，我們建議進行下列設定：

- **會議模式** 為 **自動**
- **Attendant** 路由 **的路由方法**
- **以目前狀態為基礎的路由** 至 **On**
- **代理人警示時間****：20 秒**

## <a name="call-overflow-handling"></a>呼叫溢出處理

![通話溢位設定螢幕擷取畫面](media/call-queue-overflow-handling.png)

**佇列中的通話數目上限** 指定在任何指定時間都可以在佇列中等候的通話數目上限。 預設值為 50，但範圍從 0 到 200。 達到此限制時，會依照達到通話數上限設定所指定的處理 **通話。**

您可以選擇中斷通話的中斷，或是將電話重新導向至任何通話路由目的地。 例如，您可能會要求來電者在佇列中為代理人留下語音信箱。 針對外部移轉，請參閱先決條件和[](plan-auto-attendant-call-queue.md#prerequisites)外部電話號碼移轉[-](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)號碼格式的技術詳細資料。

> [!NOTE]
> 如果通話數上限設定為 0，將不會播放問候語訊息。

## <a name="call-timeout-handling"></a>通話超時處理

![通話超時設定螢幕擷取畫面](media/call-queue-timeout-handling.png)

**通話超時：最大等待時間** 可指定通話在重新導向或中斷連接前可保留佇列中的時間上限。 您可以指定 0 秒到 45 分鐘的值。

您可以選擇中斷通話的中斷，或是將電話重新導向至其中一個通話路由目的地。 例如，您可能會要求來電者在佇列中為代理人留下語音信箱。 針對外部移轉，請參閱先決條件和[](plan-auto-attendant-call-queue.md#prerequisites)外部電話號碼移轉[-](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)號碼格式的技術詳細資料。

當您已選取通話超時選項時，請按一下 **[儲存**。

## <a name="caller-id-for-outbound-calls"></a>外電來電的本機號碼

由於通話佇列的代理人可以撥出以傳回客戶電話，因此請考慮將通話佇列成員的本機號碼設定為適當自動語音回應的服務號碼。 詳細資訊 [請參閱 Microsoft Teams 中的管理來電](caller-id-policies.md) 顯示政策。

## <a name="supported-clients"></a>支援的用戶端

通話佇列的通話代理程式支援下列用戶端：

  - 商務用 Skype 桌面用戶端 2016 (32 位和 64 位版本) 
  - Lync 桌面用戶端 2013 (32 位和 64 位版本) 
  - Microsoft Teams 支援的所有 IP 電話型號。 請參閱 [取得商務用 Skype Online 的電話](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)。
  - Mac 商務用 Skype 用戶端 (版本 16.8.196 及更新版本) 
  - Android 商務用 Skype 用戶端 (6.16.0.9 及更新版本) 
  - iPhone 商務用 Skype 用戶端 (6.16.0 及更新版本) 
  - iPad 商務用 Skype 用戶端 (6.16.0 及更新版本) 
  -  (32 位和 64 位版本的 Microsoft Teams Windows 用戶端) 
  - Microsoft Teams Mac 用戶端
  - Microsoft Teams iPhone 應用程式
  - Microsoft Teams Android 應用程式

    > [!NOTE]
    > 指派直接路由號碼的通話佇列不支援商務用 Skype 用戶端、Lync 用戶端或商務用 Skype IP 電話代理程式。

## <a name="call-queue-cmdlets"></a>通話佇列 Cmdlet

您也可以使用 Windows PowerShell 來建立和設定通話佇列。 以下是您用於管理通話佇列的 Cmdlet。

- [New-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue)

- [Set-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue)

- [Get-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue)

- [Remove-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue)

## <a name="related-topics"></a>相關主題

[以下是可透過電話系統獲得的功能](here-s-what-you-get-with-phone-system.md)

[取得服務電話號碼](getting-service-phone-numbers.md)

[音訊會議與通話方案的適用國家/地區](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance)

[Windows PowerShell 與 Lync Online 的簡介](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
