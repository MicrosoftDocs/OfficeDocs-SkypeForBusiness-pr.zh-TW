---
title: 在 Microsoft 團隊中建立通話佇列
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
description: 瞭解如何在 Microsoft 團隊中設定電話聯絡佇列，提供問候語、等候音樂、呼叫重新導向及其他功能。
ms.openlocfilehash: d696b37f95d06c529aa330bd77e2ec91e1ffc9ad
ms.sourcegitcommit: 7575fb476a594d70084c603e508dd311ef1d7edb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/05/2021
ms.locfileid: "49765414"
---
# <a name="create-a-call-queue"></a>建立通話佇列

通話佇列提供將呼叫者路由給組織中的人員的方法，可協助您解決特定問題。 呼叫會一次散佈給佇列中的人員， (稱為 [ *代理* 程式]) 。 

通話佇列提供：

- 問候訊息。

- 當人員在佇列中等待保留時，請使用音樂。

- 呼叫路由-先進先 *出* (FIFO) 訂單至代理程式。

- [佇列溢出] 和 [超時] 的處理選項。

請確定您已閱讀 [小組自動語音應答] [和 [呼叫佇列](plan-auto-attendant-call-queue.md) ] 的 [規劃]，然後依照本文中的程式執行 [步驟](plan-auto-attendant-call-queue.md#getting-started) 。

若要設定通話佇列，請在 [團隊管理中心] 中，展開 [ **語音**]，按一下 [ **通話佇列**]，然後按一下 [ **新增**]。

## <a name="resource-account-and-language"></a>資源帳戶和語言

![資源帳戶和語言設定的螢幕擷取畫面](media/call-queue-name-language.png)

1. 輸入通話佇列的名稱。 當代理程式從佇列接收來電時，就會看到這個名稱。

2. 按一下 [ **新增帳戶**]，搜尋您要與此通話佇列搭配使用的資源帳戶，按一下 [ **新增**]，然後按一下 [ **新增**]。

3. 選擇語言。 此語言將用於系統產生的語音提示，以及語音信箱操作 (如果您) 啟用這些語言。

## <a name="greetings-and-music-on-hold-in-queue"></a>[在佇列中保留問候語] 和 [音樂]

指定是否要在來電者到達佇列時，向呼叫者播放問候語。 您必須上傳包含您要播放之問候語的 MP3、WAV 或 WMA 檔案。

當來電者在佇列中保留時，小組會將預設音樂提供給呼叫者。 如果您想要播放特定音訊檔案，請選擇 [ **播放音訊** 檔案]，然後上傳 MP3、WAV 或 WMA 檔案。

> [!NOTE]
> 上傳的錄製不能超過 5 MB。
> 小組通話佇列中提供的預設音樂，由貴組織所提供的任何版稅免費提供。 

## <a name="call-agents"></a>撥號代理程式

請參考 [必備元件](plan-auto-attendant-call-queue.md#prerequisites) ，以便能夠將代理新增至通話佇列。

![通話佇列之使用者與群組設定的螢幕擷取畫面](media/call-queue-users-groups.png)

您可以透過群組新增最多20個代理程式，以及最多200個代理程式。

若要將使用者新增至佇列，請按一下 [ **新增使用者**]，搜尋使用者，按一下 [ **新增**]，然後按一下 [ **新增**]。

若要在佇列中新增群組，請按一下 [ **新增群組**]，搜尋群組，按一下 [ **新增**]，然後按一下 [ **新增**]。 您可以使用通訊群組清單、安全性群組，以及 Microsoft 365 群組或 Microsoft 團隊小組。

> [!NOTE]
> 新增至群組的新使用者最多可能需要八個小時的時間，才能讓初次通話到達。

## <a name="call-routing"></a>通話路由

![[會議模式] 與 [路由方法] 設定的螢幕擷取畫面](media/call-queue-conference-mode-routing-method.png)

在工程師接受通話之後，**會議模式** 會大大減少呼叫者連線至代理程式所需的時間長度。 若要使用會議模式，通話佇列中的代理程式必須使用下列其中一個用戶端：

  - 最新版本的 Microsoft 團隊桌面用戶端、Android 應用程式或 iOS 應用程式
  - Microsoft 團隊手機版本 1449/1.0.94.2020051601 或更新版本
  
必須將代理的小群組帳戶設定為 [僅限團隊模式]。 不符合需求的工程師不會包含在通話傳送清單中。 如果您的代理全部使用相容的用戶端，我們建議您為通話佇列啟用會議模式。

> [!NOTE]
> [會議模式] 不支援 [忙碌] 功能。 如果未啟用目前狀態路由，非呼叫佇列呼叫上的代理程式可能仍會顯示呼叫佇列呼叫。

**路由方法** 決定了代理從佇列接收呼叫的順序。 從這些選項中選擇：

- [**助理路由**] 會同時響鈴佇列中的所有代理程式。 第一個呼叫代理程式接聽電話，即可取得通話。

- **串列路由** 依 **來電代理** 程式清單中指定的順序，逐一響鈴所有呼叫代理程式。 如果代理程式關閉或沒接聽來電，該通話會撥打下一個代理程式，並嘗試所有的代理程式，直到它被挑選或超時為止。

- **迴圈法** 會平衡來電的路由，讓每個通話代理程式從佇列取得相同數量的呼叫。 這在入站銷售環境中可能是您想要的，以確保所有通話代理程式之間有同等的機會。

- 閒置時間最長的 **閒置** 路由，每個呼叫都是閒置時間最長的代理程式。 如果工程師的目前狀態為 [空閒] 或其目前狀態已離開10分鐘以內，則會被視為空閒。 目前狀態為已離開超過10分鐘的代理程式不會被視為空閒，而且將無法接收來電，直到它們變更其目前狀態。 

![[路由]、[選擇外移] 及 [提醒時間] 設定的螢幕擷取畫面](media/call-queue-presence-agents-time.png)


目前 **狀態路由** 會使用呼叫代理程式的可用性狀態，判斷是否應將工程師納入所選路由方法的通話路由清單中。 [通話傳送] 清單中包含 [ **提供給可用** ] 的呼叫代理程式，並可接聽來電。 其可用性狀態設定為任何其他狀態的代理會從 [呼叫傳送清單] 中排除，而且在其可用性狀態變更回 [ **可用**] 之前，將不會收到來電。 

您可以使用任何一種路由方法來啟用目前狀態的呼叫路由。

如果代理程式無法取得來電，無論其可用性狀態為何，都不會包含在通話傳送清單中。 

> [!NOTE]
> 啟用商務用 Skype 用戶端的代理程式不會包含在 [通話] 路由清單中（如果已啟用目前狀態路由的話）。 如果您有使用商務用 Skype 的代理商，請不要啟用目前狀態的呼叫路由。

**Agent 警示時間** 指定在佇列將呼叫重新導向至下一個代理程式之前，該電話會響鈴的時間。

對於大量的佇列，我們建議您進行下列設定：

- **自動** 進行 **會議模式**
- **傳送路由方法** 來 **傳送路由**
- [目前 **狀態] 路由** 至 [**開啟**]
- **Agent 提醒時間：** **20 秒**

## <a name="call-overflow-handling"></a>呼叫溢出處理

![通話溢出設定的螢幕擷取畫面](media/call-queue-overflow-handling.png)

**佇列中的最大通話** 數指定可在任何指定時間在佇列中等待的呼叫數量上限。 預設值為50，但範圍可以是0到200。 達到這個限制之後，就會按照在 **達到最大通話數設定時** 所指定的方式來處理通話。

您可以選擇中斷通話，或將它重新導向至任何呼叫路由目標。 例如，您可能會有來電者在佇列中留下代理程式的語音信箱。 如需外部轉接，請參閱 [先決條件](plan-auto-attendant-call-queue.md#prerequisites) 與 [外部電話號碼轉接-技術詳細資料](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) ，瞭解數位格式設定。

> [!NOTE]
> 如果 [呼叫數量上限] 設定為0，則不會播放問候語訊息。

## <a name="call-timeout-handling"></a>通話超時處理

![通話超時設定的螢幕擷取畫面](media/call-queue-timeout-handling.png)

[**通話超時]： [最長等候時間**] 指定在電話重新導向或中斷前，可以在佇列中保留的最長時間。 您可以指定0秒到45分鐘的值。

您可以選擇中斷通話，或將它重新導向至其中一個呼叫路由目標。 例如，您可能會有來電者在佇列中留下代理程式的語音信箱。 如需外部轉接，請參閱 [先決條件](plan-auto-attendant-call-queue.md#prerequisites) 與 [外部電話號碼轉接-技術詳細資料](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) ，瞭解數位格式設定。

選取您的通話超時選項之後，按一下 [ **儲存**]。

## <a name="caller-id-for-outbound-calls"></a>撥出電話的本機號碼

由於呼叫佇列中的代理程式可能會撥出以傳回客戶電話，因此請考慮將呼叫佇列成員的本機號碼設定為適當的自動語音應答的服務號碼。 如需詳細資訊，請參閱 [在 Microsoft 團隊中管理本機號碼原則](caller-id-policies.md) 。

## <a name="supported-clients"></a>支援的用戶端

通話佇列中的呼叫代理程式支援下列用戶端：

  - 商務用 Skype desktop 用戶端 2016 (32 位與64位版本) 
  - Lync 桌面用戶端 2013 (32 位與64位版本) 
  - Microsoft 團隊支援的所有 IP 電話模型。 請參閱 [取得商務用 Skype Online 的電話](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)。
  - Mac 版商務用 Skype 用戶端 (版本16.8.196 及更新版本) 
  - Android 版商務用 Skype 用戶端 (版本6.16.0.9 及更新版本) 
  - iPhone 版商務用 Skype 用戶端 (版本6.16.0 及更新版本) 
  - iPad 版商務用 Skype 用戶端 (版本6.16.0 及更新版本) 
  - Microsoft 團隊 Windows 用戶端 (32 位與64位版本) 
  - Microsoft 團隊 Mac 用戶端
  - Microsoft 團隊 iPhone 應用程式
  - Microsoft 團隊 Android 應用程式

    > [!NOTE]
    > 指派直接傳送號碼的呼叫佇列不支援商務用 Skype 用戶端、Lync 用戶端或商務用 Skype IP 手機做為代理程式。

## <a name="call-queue-cmdlets"></a>通話佇列 Cmdlet

您也可以使用 Windows PowerShell 來建立及設定通話佇列。 以下是您用來管理通話佇列的 Cmdlet。

- [新-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue)

- [Set-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue)

- [CsCallQueue](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue)

- [移除-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue)

## <a name="related-topics"></a>相關主題

[以下是可透過電話系統獲得的功能](here-s-what-you-get-with-phone-system.md)

[取得服務電話號碼](getting-service-phone-numbers.md)

[音訊會議與通話方案的適用國家/地區](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[新-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance)

[Windows PowerShell 與 Lync Online 的簡介](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
