---
title: 在 Microsoft 團隊中建立通話佇列-小型企業教學課程
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: colongma
ms.topic: article
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
description: 瞭解如何使用 Microsoft 365 商務版語音設定通話佇列。
ms.openlocfilehash: 10bc19f122daab89c91a01db0ffa31f48739d96d
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909614"
---
# <a name="create-a-call-queue---small-business-tutorial"></a>建立通話佇列-小型企業教學課程

通話佇列提供將呼叫者路由給組織中的人員的方法，可協助您解決特定問題。 呼叫會一次散佈給佇列中的人員， (稱為 [ *代理* 程式]) 。 

通話佇列提供：

- 問候訊息。

- 當人員在佇列中等待保留時，請使用音樂。

- 呼叫路由-先進先 *出* (FIFO) 訂單至代理程式。

- [佇列溢出] 和 [超時] 的處理選項。

#### <a name="before-you-begin"></a>開始之前

取得一些 [電話系統-虛擬使用者授權（](../teams-add-on-licensing/virtual-user.md) 如果您還沒有的話）。 針對您規劃設定的每個通話佇列和自動語音應答，取得一個。 這些授權是免費的，因此我們建議您先取得幾個額外的案例，以備日後決定變更您的設定。

由於通話佇列中的代理程式可能會撥出以傳回客戶電話，因此請考慮將來電代理程式的本機號碼設定為您的主要電話號碼或適當的自動語音應答號碼。 如需詳細資訊，請參閱 [在 Microsoft 團隊中管理本機號碼原則](../caller-id-policies.md) 。

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-call-queue"></a>請依照下列步驟來設定您的通話佇列

# <a name="step-1brcreate-a-team"></a>[步驟 1 <br> 建立小組](#tab/create-team)

建立通話佇列時，您可以將個別使用者新增至佇列，或者您可以使用現有的安全性群組、Microsoft 365 群組或 Microsoft 團隊小組。 我們建議使用團隊。 這可讓佇列中的成員彼此聊天、分享想法，以及建立檔或其他資源，協助客戶進行協助。 小組也會提供語音信箱，讓來電者在數小時後離開訊息，或當佇列達到其最大容量時。

建立小組

1. 首先，按一下應用程式左側的 [ **小組** ]，然後按一下團隊清單底部的 [ **加入] 或 [建立小組** ]。

2. 然後按一下 [ **建立團隊** (第一張卡片，左上角) ]。

3. 選擇 [ **從頭開始建立小組**]。

4. 接下來，選擇您要的是公用或私人團隊。 我們建議您在通話佇列中使用 **私人** ，以避免人員透過加入小組而無意中成為佇列的一部分。

5. 為您的小組命名，並新增選用的描述。

6. 完成後，請按一下 [ **建立**]。

8. 輸入您想在通話佇列中擁有的人員名稱，然後按一下 [ **新增**]。

9. 按一下 [ **關閉**]。 您新增至小組的人員會收到一封電子郵件，讓他們知道他們現在是您的小組成員，而且小組會顯示在他們的小組清單中。

> [!div class="nextstepaction"]
> [步驟 2-資源帳戶 >](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=resource-account#steps)

# <a name="step-2brresource-accounts"></a>[步驟 2 <br> 資源帳戶](#tab/resource-account)

您建立的每個通話佇列都需要有資源帳戶。 這與使用者帳戶類似，只是帳戶與自動語音應答或通話佇列無關，而不是寄件者。 在此步驟中，我們會建立帳戶，將它指派為 *Microsoft 365 電話系統-虛擬使用者* 授權，然後使用它來開始建立通話佇列。

### <a name="create-a-resource-account"></a>建立資源帳戶

您可以在 [團隊管理中心] 中建立資源帳戶。

1. 在 [團隊管理中心] 中，展開 [ **整個組織的設定**]，然後按一下 [ **資源帳戶**]。

2. 按一下 [ **新增**]。

3. 在 [ **新增資源帳戶** ] 窗格中，填寫 [ **顯示名稱**]、[使用者名稱 **]，然後** 選擇 [ **通話佇列** ] 作為 **資源帳戶類型**。

    ![[新增資源帳戶] 使用者介面的螢幕擷取畫面](../media/resource-account-add-cq.png)

4. 按一下 **[儲存]**。

新帳戶將會出現在帳戶清單中。

![資源帳戶清單的螢幕擷取畫面](../media/resource-accounts-page.png)

### <a name="assign-a-license"></a>指派授權

您必須將 *Microsoft 365 電話系統-虛擬使用者* 授權指派給資源帳戶。

1. 在 Microsoft 365 系統管理中心，按一下您要指派授權的資源帳戶。

2. 在 [ **授權及應用程式** ] 索引標籤的 [ **授權**] 底下，選取 [ **Microsoft 365 電話系統-虛擬使用者**]。

3. 按一下 [ **儲存變更**]。

    ![在 Microsoft 365 系統管理中心指派授權使用者介面的螢幕擷取畫面](../media/resource-account-assign-virtual-user-license.png)

### <a name="create-a-call-queue"></a>建立通話佇列

接下來，我們將開始建立新的通話佇列並指派資源帳戶。

1. 在 [團隊管理中心] 中，展開 [ **語音**]，按一下 [ **通話佇列**]，然後按一下 [ **新增**]。

1. 輸入通話佇列的名稱。 當代理程式從佇列接收來電時，就會看到這個名稱。

2. 按一下 [ **新增帳戶**]，搜尋您要與此通話佇列搭配使用的資源帳戶，按一下 [ **新增**]，然後按一下 [ **新增**]。

3. 選擇語言。 此語言將用於系統產生的語音提示，以及語音信箱操作 (如果您) 啟用這些語言。

    ![資源帳戶和語言設定的螢幕擷取畫面](../media/call-queue-name-language.png)

4. 指定是否要在來電者到達佇列時，向呼叫者播放問候語。 您必須上傳包含您要播放之問候語的 MP3、WAV 或 WMA 檔案。

5. 當來電者在佇列中保留時，小組會將預設音樂提供給呼叫者。 如果您想要播放特定音訊檔案，請選擇 [ **播放音訊** 檔案]，然後上傳 MP3、WAV 或 WMA 檔案。

> [!NOTE]
> 上傳的錄製不能超過 5 MB。
> 小組通話佇列中提供的預設音樂，由貴組織所提供的任何版稅免費提供。 

> [!div class="nextstepaction"]
> [步驟 3-通話代理程式 >](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=call-agents#steps)

# <a name="step-3brcall-agents"></a>[步驟3： <br> 撥號代理程式](#tab/call-agents)

若要將代理程式新增到通話佇列，我們將新增我們先前建立的小組。

1. 按一下 [ **新增群組**]。
2. 輸入您建立的小組名稱。
3. 按一下 [ **新增**]，然後按一下 [ **新增**]。

    ![通話佇列之使用者與群組設定的螢幕擷取畫面](../media/call-queue-users-groups-smb.png)

您可以透過群組或團隊新增最多20個代理程式，以及最多200個代理程式。

> [!NOTE]
> 在小組中新增新的使用者時，最多可能需要八個小時的時間，才能讓初次通話到達。

> [!div class="nextstepaction"]
> [步驟 4-資源帳戶 >](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=call-routing#steps)

# <a name="step-4brcall-routing"></a>[步驟 4 <br> 呼叫路由](#tab/call-routing)

選擇您想要使用的通話路由方法。

1. 將 [ **會議模式]** 設定為 [ **自動**]。

2. 選擇您要使用的 **路由方法** 。 這會決定代理從佇列接收呼叫的順序。 我們建議 **串列路由** 或  **迴圈**。 從這些選項中選擇：

    - [**助理路由**] 會同時響鈴佇列中的所有代理程式。 第一個呼叫代理程式接聽電話，即可取得通話。

    - **串列路由** 逐一響鈴所有呼叫代理程式。 如果代理程式關閉或沒接聽來電，該通話會撥打下一個代理程式，並嘗試所有的代理程式，直到它被挑選或超時為止。

    - **迴圈法** 會平衡來電的路由，讓每個通話代理程式從佇列取得相同數量的呼叫。 這在入站銷售環境中可能是您想要的，以確保所有通話代理程式之間有同等的機會。

    - 閒置時間最長的 **閒置** 路由，每個呼叫都是閒置時間最長的代理程式。 [目前狀態] 為「已離開超過10分鐘的代理程式] 不會包含在其中。 )  (

    ![[會議模式] 與 [路由方法] 設定的螢幕擷取畫面](../media/call-queue-conference-mode-routing-method.png)

3. 開啟 [目前 **狀態] 路由** 。 此路由會呼叫目前狀態為 [ **可用**] 的代理程式。

4. 選擇您是否要允許代理退出通話。

5. 設定 **代理程式警示時間** ，以指定在佇列將呼叫重新導向至下一部代理程式之前，電話會響鈴的時間。

    ![[路由]、[選擇外移] 及 [提醒時間] 設定的螢幕擷取畫面](../media/call-queue-presence-agents-time.png)

> [!div class="nextstepaction"]
> [步驟 5-呼叫溢出 >](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=call-overflow#steps)

# <a name="step-5brcall-overflow"></a>[步驟 5 <br> 通話溢出](#tab/call-overflow)

選擇您想要如何處理超過佇列中最大值的通話。

1. 設定 **佇列中的最大通話** 數。

2. 選擇達到最大通話數時要執行的動作。 您可以中斷通話或重新導向。 我們建議您將來電重新導向至下列其中一個目的地：
    - **組織中的人員** -您組織中能夠接聽語音通話的人員
    - **語音 app** -自動語音應答或其他通話佇列。  (選擇 [選擇此目的地時，與自動語音應答或通話佇列] 相關聯的資源帳戶。 ) 
    - **外部電話號碼** -任何電話號碼。 使用此格式： + [國家/地區碼] [區域碼] [電話號碼]
    - **語音信箱** -您可以使用您所建立之小組的語音信箱。

    ![通話溢出設定的螢幕擷取畫面](../media/call-queue-overflow-handling.png)

> [!div class="nextstepaction"]
> [步驟 6-通話超時 >](https://review.docs.microsoft.com/microsoftteams/business-voice/create-a-phone-system-call-queue-smb?branch=mikeplum-smb-voice&tabs=call-timeout#steps)

# <a name="step-6brcall-timeout"></a>[步驟 6 <br> 通話超時](#tab/call-timeout)

選擇當通話在佇列中等待的時間太長時要發生的情況。

1. 設定 **通話超時：最長等待時間**。

2. 選擇來電超時時要執行的動作。您可以中斷通話或重新導向。 我們建議您將來電重新導向至下列其中一個目的地：
    - **組織中的人員** -您組織中能夠接聽語音通話的人員
    - **語音 app** -自動語音應答或其他通話佇列。  (選擇 [選擇此目的地時，與自動語音應答或通話佇列] 相關聯的資源帳戶。 ) 
    - **外部電話號碼** -任何電話號碼。 使用此格式： + [國家/地區碼] [區域碼] [電話號碼]
    - **語音信箱** -您可以使用您所建立之小組的語音信箱。

    ![通話超時設定的螢幕擷取畫面](../media/call-queue-timeout-handling.png)

3. 按一下 **[儲存]**。

這樣就完成了您的通話佇列設定。 接下來，您可能會想要 [設定自動](create-a-phone-system-auto-attendant-smb.md)語音應答。

---

