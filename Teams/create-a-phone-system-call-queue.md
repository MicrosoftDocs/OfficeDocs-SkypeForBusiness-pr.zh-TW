---
title: 建立通話佇列
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: phans, wasseemh
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.callqueues.overview"
ms.custom:
- Phone System
description: 瞭解如何在 Microsoft 團隊中設定雲端通話佇列的電話系統。
ms.openlocfilehash: fc7cc9558036d30d388a279ac155fe6382e611a8
ms.sourcegitcommit: 15fe483079847d24869e325eead35f252da8c7dd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/06/2019
ms.locfileid: "37972494"
---
# <a name="create-a-cloud-call-queue"></a>建立雲端通話佇列

雲端通話佇列可以提供：

- 問候訊息。
- 當人員正在等候時，請播放音樂。
- 在已啟用郵件的通訊群組清單和安全性群組中，將呼叫重新導向至呼叫代理程式。
- 設定不同的參數，例如佇列大小上限、超時及呼叫處理選項。

您可以使用[資源帳戶](manage-resource-accounts.md)將電話號碼與通話佇列建立關聯。 通話佇列可以直接撥號，或由自動語音應答上的選取進行存取。

來電者在暫停時，會聽到音樂，且通話會連線至呼叫代理程式 *（先進先出*（FIFO）訂單）。

佇列中的所有通話都是透過下列其中一種方法傳送給代理：

- 使用 [傳送助理] 時，佇列中的第一個呼叫會同時響鈴所有的 agent。
- 在串列路由中，佇列中的第一個呼叫會逐一響鈴一個呼叫代理程式。
- 使用迴圈法，傳入通話的路由會平衡，讓每個呼叫代理程式從佇列取得相同數量的呼叫。

    > [!NOTE]
    > 呼叫已**離線**、將其目前狀態設定為 [**請勿打擾]，** 或自願退出通話佇列的代理程式將不會收到來電。

- 一次只有一個來電通知（適用于佇列頭的呼叫）會傳送給呼叫代理程式。
- 通話代理程式接受通話之後，佇列中的下一個來電就會開始撥打通話代理程式。

> [!NOTE]
> 本文適用于 Microsoft 團隊和商務用 Skype Online。

## <a name="step-1--get-started"></a>步驟1：快速入門

若要開始使用通話佇列，請務必記住以下幾點：

- 需要通話佇列，才能擁有關聯的資源帳戶。 如需資源帳戶的詳細資訊，請參閱[管理團隊中的資源帳戶](manage-resource-accounts.md)。
- 當您將電話號碼指派給資源帳戶時，您現在可以使用 [免付費電話系統[虛擬使用者授權](teams-add-on-licensing/virtual-user.md)]。 [電話系統] 可讓組織階層的電話號碼與低成本的自動語音應答及呼叫佇列服務搭配使用。

> [!NOTE]
> 僅限 Microsoft 團隊使用者和代理程式支援電話佇列的直接路由服務號碼。

> [!NOTE]
> 若要將來電重新導向至貴組織中的線上人員，他們必須具備**電話系統**授權，且可供企業語音使用或擁有 Office 365 通話方案。 請參閱[指派商務用 Skype 授權](/Skype/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)或[指派 Microsoft 團隊授權](assign-teams-licenses.md)。 若要啟用企業語音，您可以使用 Windows PowerShell。 例如，執行：`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

- 若要深入瞭解 Office 365 通話方案，請參閱[手機系統和通話方案](calling-plan-landing-page.md)與[Office 365 的通話方案](calling-plans-for-office-365.md)。

- 您只能將雲端電話列隊指派給您在**Microsoft 團隊系統管理中心**取得或從其他服務提供者轉接的免付費服務電話號碼。 免付費服務號碼需要通訊點數。

    > [!NOTE]
    > 無法將使用者（訂閱者）電話號碼指派給呼叫佇列-只有服務付費電話或免付費電話號碼可供使用。

- 下列用戶端支援與雲端通話佇列相關聯的通話代理程式：

  - 商務用 Skype desktop 用戶端2016（32位與64位版本）

  - Lync 桌面用戶端2013（32位與64位版本）

  - Microsoft 團隊支援的所有 IP 電話模型。 請參閱[取得商務用 Skype Online 的電話](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)。

  - Mac 商務用 Skype 用戶端（版本16.8.196 及更新版本）

  - Android 版商務用 Skype 用戶端（版本6.16.0.9 及更新版本）

  - iPhone 商務用 Skype 用戶端（版本6.16.0 及更新版本）

  - iPad 商務用 Skype 用戶端（版本6.16.0 及更新版本）

  - Microsoft 團隊 Windows 用戶端（32位與64位版本）

  - Microsoft 團隊 Mac 用戶端

  - Microsoft 團隊 iPhone 應用程式

  - Microsoft 團隊 Android 應用程式

    > [!NOTE]
    > 指派直接傳送號碼的通話佇列不支援商務用 Skype 用戶端、Lync 用戶端或商務用 Skype IP 手機做為代理程式。 

## <a name="step-2--getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a>步驟2：取得或轉移付費或免付費服務電話號碼

您必須先取得或轉讓現有的付費或免付費服務號碼，才能建立及設定通話佇列。 當您收到付費或免付費服務電話號碼之後，就會顯示在**Microsoft 團隊系統管理中心** > **舊版入口網站** > **語音** > **電話號碼**中，且**數位類型**會列為**服務-** 免費。 若要取得您的服務號碼，請參閱[取得服務電話號碼](getting-service-phone-numbers.md)，或者如果您想要轉移現有的服務號碼，請參閱[將電話號碼轉移至團隊](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)。

> [!NOTE]
> 如果您在美國以外，您就無法使用 Microsoft 團隊系統管理中心來取得服務號碼。 移至 [[管理貴組織的電話號碼](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)]，瞭解如何從美國以外的地區進行。

設定多個自動語音應答時，您可能只會將電話號碼指派給主要的自動助理資源帳戶，這可以讓呼叫者直接加入通話佇列或嵌套自動語音應答。 在這些情況下，您不需指派撥號鍵台選項，就能在您的系統中建立所有自動語音應答及呼叫佇列，然後在稍後編輯設定。 這是必要的，因為您不允許建立連結至通話佇列的選項，或是不存在的自動語音應答。

## <a name="step-3--create-a-new-call-queue"></a>步驟3：建立新的通話佇列

[!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

> [!IMPORTANT]
> 每個通話佇列都必須有一個相關聯的[資源帳戶](manage-resource-accounts.md)。 您必須先建立資源帳戶，然後才能將它與通話佇列建立關聯。

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft 團隊系統管理中心

在**Microsoft 團隊系統管理中心**、**語音** > **通話佇列**中，按一下 [ **+ 新增**]：

### <a name="set-the-call-queue-display-name-and-resource-account"></a>設定通話佇列顯示名稱和資源帳戶

![含編號標注的新通話佇列的螢幕擷取畫面](media/37ecc300-a108-4294-8463-fce570dfce72.png)

* * *

![在前一個螢幕擷取畫面](media/sfbcallout1.png)
**名稱**中參照標注的數位1圖示輸入通話佇列的描述性顯示名稱。 這個名稱是必要的，而且最多可以包含64個字元，包括空格。

 此名稱會顯示在撥入通話的通知中。

* * *

![在前一個螢幕擷取畫面中參照標注的數位2的圖示](media/sfbcallout2.png)

**新增帳戶**選取資源帳戶。 資源帳戶可以或不與電話號碼的服務付費或免付費電話號碼相關聯，但每個通話佇列都需要相關聯的資源帳戶。

如果沒有列出任何專案，您必須先取得服務號碼並將其指派給資源帳戶，然後才能建立此通話佇列（如前文所述）。 若要取得您的服務號碼，請參閱[取得服務電話號碼](getting-service-phone-numbers.md)。 如果您希望通話佇列擁有相關聯的電話號碼，請按照[管理團隊中的資源帳戶](manage-resource-accounts.md)中所述的方式來建立資源帳戶。

> [!NOTE]
> 如果您想要或需要指派**網域**，您可以將它指派給通話佇列的資源帳戶。

### <a name="set-the-greeting-and-music-played-while-on-hold"></a>設定保留時播放的問候語和音樂

![含編號標注的問候和音樂選項螢幕擷取畫面](media/1d395a93-7cab-4178-9295-12d5379e20de.png)

* * *

![在前一個螢幕擷取畫面中參照標注的數位1圖示](media/sfbcallout1.png)

[**問候語**] 是選擇性的。 這是呼叫撥入電話號碼的使用者所播放的問候語。

您可以上傳音訊檔（.wav、mp3 或 .wma 格式）。

![在前一個螢幕擷取畫面中參照標注的數位2的圖示](media/sfbcallout2.png)

**等候音樂**您可以將預設的音樂保留在通話佇列中，或者您可以將音訊檔案上傳成 .wav、mp3 或 .wma 格式，以供您的自訂音樂保留使用。

* * *

### <a name="select-the-call-answering-options"></a>選取呼叫應答選項

![含編號標注的通話應答選項之螢幕擷取畫面](media/5d249515-d532-4af2-90da-011404028b89.png)

![在前一個螢幕擷取畫面中參照標注的數位1圖示](media/sfbcallout1.png)

您最多可以選取200呼叫代理程式，其屬於下列任何一種郵寄清單或群組：

- Office 365 群組
- 安全性群組
- 通訊群組清單

所選取的通話代理程式必須是下列其中一項： 

- 已啟用手機系統授權和企業語音的線上使用者 
- 使用通話方案的線上使用者
- 內部部署商務用 Skype 伺服器使用者

  > [!NOTE]
  > 如果您想要將來電重新導向至組織中線上的人員，也適用這種情況。 這些人必須具備**手機系統**授權和企業語音功能，**或是**有通話方案。 如需詳細資訊，請參閱[指派商務用 Skype 授權](/Skype/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)、[指派 Microsoft 團隊授權](https://docs.microsoft.com/microsoftteams/assign-teams-licenses)，或適合[您的通話計畫？](https://docs.microsoft.com/microsoftteams/calling-plan-landing-page)

 若要啟用企業語音的代理程式，您可以使用 Windows PowerShell。 例如，執行：`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

- 已新增至 Office 365 群組的**電話系統**授權或通話方案的使用者;已啟用郵件的通訊群組清單;或 [安全性群組]。 在通訊群組清單或安全性群組中，新新增的代理程式可能需要長達3小時，才能開始從通話佇列接收通話。 新建立的通訊群組清單或安全性群組可能需要長達48小時才能與通話佇列搭配使用。 新建立的 Office 365 群組幾乎會立即提供給您。

- 如果您的代理程式是使用 Microsoft 團隊 App 接聽通話佇列通話，則必須在 TeamsOnly 模式中。

![[新增撥號代理程式] 窗格的螢幕擷取畫面](media/skype-for-business-add-agents-to-call-queue.png)

![在前一個螢幕擷取畫面中參照標注的數位2的圖示](media/sfbcallout2.png)

**路由方法**您**可以為通話**佇列發佈方法選擇 [行事等]、[**串列**] 或 [**迴圈**]。 所有新的和現有的通話佇列都會依預設選取 [助理] 路由。 使用 [接聽] 路由時，佇列中的第一次呼叫會同時響鈴所有呼叫代理程式。 第一個呼叫代理程式接聽電話，即可取得通話。

- [行事鈴**路由**] 會讓佇列中的第一個呼叫同時撥打所有通話代理程式。 第一個呼叫代理程式接聽電話，即可取得通話。
- 從呼叫代理程式清單的開頭開始，逐一撥打電話**給來電代理**程式。 無法在通話代理程式清單中排序代理程式。 如果代理程式關閉或沒接聽電話，通話會撥打清單中的下一個代理程式，並一次嘗試一個代理程式，直到在佇列中被拾取或等待超時為止。
  > [!NOTE]
  > 串列路由會略過**離線**、將其目前狀態設定為 [**請勿打擾**]，或已**選擇**不在此佇列中取得呼叫的代理程式。
- **迴圈**平衡：將來電進行路由，讓每個通話代理程式從佇列取得相同數目的呼叫。 這在入站銷售環境中可能是您想要的，以確保所有通話代理程式之間有同等的機會。

### <a name="select-an-agent-opt-out-option"></a>選取代理退出宣告選項

![含編號標注的代理退出宣告選項的螢幕擷取畫面](media/99279eff-db61-4acf-9b62-64be84b6414b.png)

* * *

![在前一個螢幕擷取畫面中參照標注的數位1圖示](media/sfbcallout1.png)

**工程師可以選擇不接聽電話**您可以透過啟用此選項，選擇允許呼叫佇列代理程式退出宣告來自特定佇列的呼叫。

啟用此選項可讓此佇列中的所有代理程式從該呼叫佇列開始或停止接聽通話。 您隨時都可以取消選取核取方塊，讓代理程式再次自動加入此佇列（所有代理的預設設定），以隨時撤銷代理自願退出許可權。

若要存取退出宣告選項，工程師可以執行下列動作：

 1. 開啟其桌面商務用 Skype 用戶端中的**選項**。
 2. 在 [**來電轉接**] 索引標籤上，按一下 [**編輯線上編輯設定**] 連結。
 3. 在 [使用者設定] 頁面上，按一下 [**通話佇列**]，然後清除任何要退出宣告之佇列的核取方塊。

    > [!NOTE]
    > 使用商務用 Skype Desktop 以外的 app 或端點的代理程式可從 [使用者設定] 入口網站[https://aka.ms/cqsettings](https://aka.ms/cqsettings)存取 [退出宣告] 選項。

![數位2的圖示，在先前的螢幕擷取畫面](media/sfbcallout2.png)
中參照標注**Agent 提醒設定**

這會定義在串列或迴圈路由方法移至下一個代理程式之前，收到呼叫通知代理程式的持續時間。

預設設定為30秒，但最多可設定3分鐘。

* * *

### <a name="set-the-call-overflow-and-timeout-handling-options"></a>設定通話溢位與超時處理選項

![含編號標注的溢出處理選項之螢幕擷取畫面](media/3f018734-16fe-458b-827d-71fc25155cde.png)

* * *

![在前一個螢幕擷取畫面中參照標注的數位1圖示](media/sfbcallout1.png)

**佇列中的最大通話**數使用此功能來設定可以同時在佇列中等候的最大通話數。 預設值為50，但範圍可以是0到200。 達到這個限制之後，就會按照您在 [**達到最大通話數**] 設定時所設定的方式來處理通話。

* * *

![在前一個螢幕擷取畫面中參照標注的數位2的圖示](media/sfbcallout2.png)

**達到最大通話數時**當通話佇列達到其大小上限時（使用 **[佇列] 設定中的最大通話**設定），您可以選擇新的來電所要採取的動作。

- **中斷**連線通話中斷連線。
- 重新**導向至**當您選擇此選項時，請選取下列其中一項：

  - **貴公司中的人員**具備**電話系統**授權且可供企業語音使用或有通話方案的線上使用者。 您可以設定它，讓來電者可以傳送給語音信箱。 若要這樣做，請選取**貴公司中的人員**，並將其呼叫權直接轉寄給語音信箱。

  若要瞭解語音信箱所需的授權，請參閱[設定雲端語音信箱](set-up-phone-system-voicemail.md)。

  - **語音應用程式**選取與已建立之通話佇列或自動助理相關聯的資源帳戶名稱。

* * *

![在前一個螢幕擷取畫面中參照標注的數位3圖示](media/sfbcallout3.png)

**通話超時：最長等待時間**您也可以決定該通話在超時之前保留多少時間，且需要重新導向或中斷連線。 重新導向的位置，取決於您設定**通話超時**設定的方式。 您可以設定從0到45分鐘的時間。

超時值可以設定為以秒為單位，以15秒為間隔。 這可讓您以較精細的細微性操作通話流程。 例如，您可以指定在30秒內未由代理程式接聽的任何通話移至目錄搜尋自動語音應答。

![在前一個螢幕擷取畫面中參照標注的數位4圖示](media/sfbcallout4.png)

**通話超時**當通話達到您在 [佇列] 設定**中等候通話**的限制時間時，您可以選擇此通話會發生的情況：

- **中斷**連線通話中斷連線。
- **將此通話重新導向至**當您選擇此選項時，您可以使用下列選項：
  - **貴公司中的人員**具備**電話系統**授權且可供企業語音或有通話方案的線上使用者。 您可以將它設定為可將呼叫的人傳送給語音信箱。 若要這樣做，請選取**貴公司中的人員**，並將其呼叫權直接轉寄給語音信箱。

  若要瞭解語音信箱所需的授權，請參閱[設定雲端語音信箱](set-up-phone-system-voicemail.md)。

  - **語音應用程式**選取與已建立之通話佇列或自動助理相關聯的資源帳戶名稱。

## <a name="change-a-users-caller-id-for-outbound-calls"></a>變更撥出通話的使用者本機號碼

您可以改為使用 CsCallingLineIdentity Cmdlet，將電話撥入**式**呼叫的本機號碼改為呼叫佇列、自動語音應答或任何服務號碼，以保護使用者的身分識別。

若要這樣做，請執行：

``` Powershell
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

然後使用**授與 CallingLineIdentity** Cmdlet 將原則套用到使用者。 若要這樣做，請執行：

``` Powershell
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

您可以[在組織中](/microsoftteams/how-can-caller-id-be-used-in-your-organization)，取得如何在組織中設定本機號碼設定的詳細資訊。

## <a name="call-queue-cmdlets"></a>通話佇列 Cmdlet

您也可以使用 Windows PowerShell 來建立及設定通話佇列。 以下是您用來管理通話佇列的 Cmdlet。

- [新-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue?view=skype-ps)

- [Set-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue?view=skype-ps)

- [CsCallQueue](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue?view=skype-ps)

- [移除-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue?view=skype-ps)

### <a name="more-about-windows-powershell"></a>深入瞭解 Windows PowerShell

- Windows PowerShell 全部說明如何管理使用者，以及允許或不允許的使用者執行。 在 Windows PowerShell 中，您可以使用單一管理點管理 Office 365 和 Microsoft 團隊，讓您有多個工作要執行，即可簡化日常作業。 若要開始使用 Windows PowerShell，請參閱以下主題：

  - [Windows PowerShell 與 Lync Online 的簡介](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [為什麼需要使用 Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- Windows PowerShell 在 Microsoft 團隊系統管理中心的速度、簡潔性和生產力上有許多優點，例如當您同時為多位使用者進行設定變更時。 請參閱下列主題，瞭解這些優點：

  - [使用 Windows PowerShell 管理 Office 365](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [設定您的 Windows PowerShell 電腦](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a>相關主題

[以下是您在 Office 365 中使用電話系統所取得的結果](here-s-what-you-get-with-phone-system.md)

[取得服務電話號碼](getting-service-phone-numbers.md)

[音訊會議與通話方案的適用國家/地區](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[新-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
