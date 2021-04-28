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
description: 瞭解如何使用 Microsoft Teams 設定電話佇列的電話系統，提供問候訊息、等候音樂、重新導向通話及其他功能。
ms.openlocfilehash: 8b4fe4283ac9734c1dc29bf33759039098578744
ms.sourcegitcommit: 03ff569a0b7a8e04d7b0ab32f370a9a537fa7fe7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/28/2021
ms.locfileid: "52064799"
---
# <a name="create-a-call-queue"></a>建立通話佇列

通話佇列提供將來電者路由給組織中可協助處理特定問題或問題的人的方法。 通話會一次一次分散給佇列中 (稱為 *代理人) 。* 

通話佇列提供：

- 問候訊息。

- 當其他人在佇列中等候時播放音樂。

- 呼叫路由 - 在 *FIFO (* 中，) 呼叫路由 - 給代理人。

- 處理佇列溢出和超時的選項。

請務必先閱讀[Teams](plan-auto-attendant-call-queue.md)自動電話機和通話佇列的規劃，並遵循[](plan-auto-attendant-call-queue.md#getting-started)開始使用的步驟，然後再遵循本文中的程式。

若要設定通話佇列，請在 Teams 系統管理中心展開 [**語音** 與通話佇列>，然後按一下 [**新增**。

## <a name="video-demonstration"></a>影片示範

這段影片顯示如何在 Teams 中建立通話佇列的基本範例。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWCF23?autoplay=false]

## <a name="resource-account-and-language"></a>資源帳戶和語言

![資源帳戶和語言設定螢幕擷取畫面](media/call-queue-name-language.png)

1. 輸入通話佇列的名稱。

2. 按一下 **[新增帳戶**，搜尋要用於此通話佇列的資源帳戶;按一下 [ **新增**，然後按一下 [ **新增**> 。  (代理人收到來電時，會看到資源帳戶名稱。) 

3. 選擇支援 [的語言](create-a-phone-system-call-queue-languages.md)。 如果您啟用語音提示，系統產生的語音提示和語音信箱 (語音信箱) 。

## <a name="greetings-and-music-on-hold-in-queue"></a>佇列中保留的問候語和音樂

指定當來電者抵達佇列時，是否要播放問候語。 您必須上傳包含您想要播放的問候語的 MP3、WAV 或 WMA 檔案。

當來電者在佇列中保留時，Teams 會提供預設音樂。 如果您想要播放特定的音訊檔案，請選擇播放音訊檔案並上傳 MP3、WAV 或 WMA 檔案。

> [!NOTE]
> 上傳的錄製不能大於 5 MB。
> Teams 通話佇列中提供的預設音樂不含貴組織支付的任何版稅。 

## <a name="call-agents"></a>通話代理人

檢查 [將代理人新加入通話佇列的先決條件](plan-auto-attendant-call-queue.md#prerequisites)。

![通話佇列的使用者和群組設定螢幕擷取畫面](media/call-queue-users-groups.png)

##### <a name="teams-channel"></a>Teams 頻道

您可以透過 Teams 頻道新增最多 200 個代理程式。

如果您想要使用 Teams 頻道 [來管理](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e)佇列，請選取 [選擇團隊 **選項** ，然後按一下 [ **新增頻道**> 。 搜尋您想要使用的團隊，選取該團隊，然後按一下 [ **新增**。 選取您想要使用的頻道，然後按一下 **[Apply.**

使用 Teams 頻道進行通話佇列時，支援下列用戶端： 

  - Microsoft Teams Windows 用戶端
  - Microsoft Teams Mac 用戶端

##### <a name="users-and-groups"></a>使用者和群組

您可以個別新增最多 20 個代理程式，並透過群組最多新增 200 個代理程式。

如果您想要將個別使用者或群組新排入佇列，請選取選擇 **使用者和群組** 選項。 

若要將使用者新增到佇列，請按一下 **[新增** 使用者，搜尋使用者，按一下 [ **新增**，然後按一下 **[新增**> 。

若要將群組新增到佇列，請按一下 [ **新增** 群組、搜尋群組、按一下 [ **新增**」，然後按一下 [ **新增**。 您可以使用通訊群組清單、安全性群組和 Microsoft 365 群組或 Microsoft Teams 團隊。

> [!NOTE]
> 新使用者新加入群組最多可能需要八小時，才能第一次通話到達。

## <a name="call-routing"></a>通話路由

![會議模式和路由方法設定螢幕擷取畫面](media/call-queue-conference-mode-routing-method.png)

**會議模式** 可大幅縮短在代理人接受通話後，來電者與代理人連上的時間量。 若要讓會議模式運作，通話佇列中的代理人必須使用下列其中一個用戶端：

  - 最新版的 Microsoft Teams 桌面用戶端、Android App 或 iOS 應用程式
  - Microsoft Teams 手機版本 1449/1.0.94.2020051601 或更新版本
  
代理人的 Teams 帳戶必須設定為 Teams-only 模式。 不符合要求的代理人不會包含在通話路由清單中。 如果您的代理人都使用相容的用戶端，我們建議您為通話佇列啟用會議模式。

> [!NOTE]
> 如果電話從已啟用位置路由的直接路由閘道路由至佇列，則不支援會議模式。

**路由方法** 會決定代理程式從佇列接收來電的順序。 從這些選項中選擇：

- **話務員路由** 會同時響鈴佇列中的所有代理程式。 第一個接電話的代理人會接到電話。

- **連續路由** 會以呼叫代理程式清單中指定的順序，一個接一個地撥打所有 **呼叫** 代理程式。 如果客服人員關閉或不接電話，來電會撥打給下一個代理人，並嘗試所有代理人，直到被接回或打出電話。

- **輪循** 機制會平衡來電的路由，讓每個通話代理程式從佇列取得相同數量的通話。 在內入銷售環境中，這一點可能相當理想，以確保所有通話代理人之間享有同等的機會。

- **最長空閒** 時間會路由每個通話給閒置時間最長的代理人。 如果代理的目前狀態為可用，或其目前狀態為離開狀態少於 10 分鐘，則視為閒置狀態。 目前狀態超過 10 分鐘的代理人不會被視為閒置狀態，且在將目前狀態變更為可用之前，將不符合接聽電話資格。 

![路由、退出宣告和通知時間設定螢幕擷取畫面](media/call-queue-presence-agents-time.png)


**目前狀態路由** 會使用呼叫代理程式的可用性狀態來判斷代理人是否應該包含在所選路由方法的呼叫路由清單中。 其可用性狀態設為可用的通話 **代理人會包含在** 通話路由清單中，而且可以接聽來電。 其可用性狀態設定為任何其他狀態的代理人會排除在通話路由清單中，且不會接聽來電，直到其可用性狀態變更回可用 **。** 

您可以使用任何路由方法啟用目前狀態型通話路由。

如果代理人選擇不接聽來電，無論他們的可用性狀態設定為什麼，他們將不會包含在通話路由清單中。 

> [!NOTE]
> 啟用目前狀態路由時，使用商務用 Skype 用戶端的代理人不會包含在通話路由清單中。 如果您有使用商務用 Skype 的代理人，請勿啟用目前狀態型通話路由。

**代理人通知** 時間會指定在佇列將通話重新導向至下一個代理人之前，代理人的電話會響鈴多久。

建議使用下列設定：

- **會議模式** 為 **自動**
- **將路由方法****路由到 Round robin** 或 **最長閒置時間**
- **目前狀態路由至** **On**
- **代理人警示時間：****至 20 秒**

> [!NOTE]
> 如果未啟用目前狀態路由，且佇列中有多個通話，系統會同時向代理人顯示這些通話，而不管其目前狀態如何。 這將會有多個通知給代理人，尤其是當某些代理人沒有接聽他們收到的初始通話時。

## <a name="call-overflow-handling"></a>呼叫溢出處理

![通話溢出設定螢幕擷取畫面](media/call-queue-overflow-handling.png)

**佇列中的通話上限** 會指定在任何指定時間可在佇列中等候的通話數上限。 預設值為 50，但範圍為 0 到 200。 達到此限制時，通話會依照達到通話次數上限設定所 **指定的方式處理** 。

您可以選擇中斷通話，或重新導向到任何通話路由目的地。 例如，您可能讓來電者為佇列中的代理人留下語音信箱。 如需外部傳輸，請參閱先決條件和外部[](plan-auto-attendant-call-queue.md#prerequisites)電話號碼傳輸[- 數位](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)格式的技術詳細資料。

> [!NOTE]
> 如果通話次數上限設為 0，則問候語訊息將不會播放。

## <a name="call-timeout-handling"></a>通話超時處理

![通話超時設定螢幕擷取畫面](media/call-queue-timeout-handling.png)

**通話超時：最長等待時間** 會指定通話在重新導向或中斷連接前，在佇列中可以保留的最大時間。 您可以指定 0 秒到 45 分鐘的值。

您可以選擇中斷通話，或重新導向到其中一個通話路由目的地。 例如，您可能讓來電者為佇列中的代理人留下語音信箱。 如需外部傳輸，請參閱先決條件和外部[](plan-auto-attendant-call-queue.md#prerequisites)電話號碼傳輸[- 數位](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details)格式的技術詳細資料。

當您已選取通話超時選項時，請按一下 [**儲存。**

## <a name="caller-id-for-outbound-calls"></a>外線通話的本機號碼

由於通話佇列中的代理人可能會撥出以傳回客戶電話，請考慮將通話佇列成員的本機號碼設定為適當的自動語音機服務號碼。 請參閱 [在 Microsoft Teams 中管理來電](caller-id-policies.md) 顯示政策以瞭解更多資訊。

## <a name="supported-clients"></a>支援的用戶端

通話佇列中的通話代理程式支援下列用戶端：

  - 商務用 Skype 桌面用戶端 2016 (32 位和 64 位版本) 
  - Lync 桌面用戶端 2013 (32 位和 64 位版本) 
  - Microsoft Teams 支援的所有 IP 電話型號。 請參閱 [取得商務用 Skype Online 的手機](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)。
  - Mac 商務用 Skype 用戶端 (版本 16.8.196 及更新版本) 
  - Android 商務用 Skype 用戶端 (版本 6.16.0.9 及更新版本) 
  - iPhone 商務用 Skype 用戶端 (版本 6.16.0 及更新版本) 
  - iPad 商務用 Skype 用戶端 (版本 6.16.0 及更新版本) 
  - Microsoft Teams Windows 用戶端 (32 位和 64 位版本) 
  - Microsoft Teams Mac 用戶端
  - Windows 虛擬桌面基礎結構上的 Microsoft [Teams](/microsoftteams/teams-for-vdi) (Windows 虛擬桌面、Citrix 和 VSoft) 
  - Microsoft Teams iPhone 應用程式
  - Microsoft Teams Android 應用程式

    > [!NOTE]
    > 指派直接路由號碼的通話佇列不支援商務用 Skype 用戶端、Lync 用戶端或商務用 Skype IP 電話代理。

## <a name="call-queue-cmdlets"></a>通話佇列 Cmdlet

您也可以使用 Windows PowerShell 建立和設定通話佇列。 以下是您用於管理通話佇列的 Cmdlet。

- [New-CsCallQueue](/powershell/module/skype/new-CsCallQueue)

- [Set-CsCallQueue](/powershell/module/skype/set-CsCallQueue)

- [Get-CsCallQueue](/powershell/module/skype/get-CsCallQueue)

- [Remove-CsCallQueue](/powershell/module/skype/remove-CsCallQueue)

## <a name="related-topics"></a>相關主題

[以下是可透過電話系統獲得的功能](here-s-what-you-get-with-phone-system.md)

[取得服務電話號碼](getting-service-phone-numbers.md)

[音訊會議與通話方案的適用國家/地區](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[New-CsOnlineApplicationInstance](/powershell/module/skype/new-csonlineapplicationinstance)

[Windows PowerShell 與 Lync Online 的簡介](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
