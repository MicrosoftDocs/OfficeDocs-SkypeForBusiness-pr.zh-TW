---
title: 設定雲端自動語音應答
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: waseemh
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
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
f1keywords: None
ms.custom:
- Phone System
description: 瞭解如何為 Microsoft 團隊設定及測試雲端自動語音應答。
ms.openlocfilehash: b1756cc58e485971157c0429e8180a5f5e507ec8
ms.sourcegitcommit: 30b4b979e20066253e32ab9e44d79c48a97e6211
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/05/2019
ms.locfileid: "37972474"
---
# <a name="set-up-a-cloud-auto-attendant"></a>設定雲端自動語音應答

自動語音應答讓其他人打電話給您的組織，並流覽功能表系統，以與正確的部門通話、呼叫佇列、人員或接線員。 您可以使用 Microsoft 團隊系統管理中心或 Powershell，為您的組織建立自動語音應答。 若要建立自動語音應答，請移至左側導覽中的 [語音]，然後選取 [**自動** > **語音**應答**新增**]。

如果您想要深入瞭解自動語音應答，請參閱[什麼是雲端自動](/microsoftteams/what-are-phone-system-auto-attendants)語音應答？

> [!NOTE]
> 本文適用于 Microsoft 團隊和商務用 Skype Online。

電話號碼不會直接指派給自動語音應答，而是與自動語音助理相關聯的[資源帳戶](manage-resource-accounts.md)。

自動語音應答的實現通常會涉及數個自動語音應答。 *第一層*自動語音應答通常會有一個已指派電話號碼的資源帳戶。 嵌套的自動語音應答是用來做為第二級功能表，*第一層*的自動語音應答會連線為通話。 *嵌套*的自動語音應答不需要將電話號碼指派給其資源帳戶。

## <a name="step-1--get-started"></a>步驟1：快速入門

- 必須有一個自動語音應答，才能擁有相關聯的資源帳戶。 如需資源帳戶及所有所需授權的詳細資料，請參閱[管理團隊中的資源帳戶](manage-resource-accounts.md)。 
 
<!-- When you create a new auto attendant in Teams after October 10th, 2019, the required auto attendant is automatically created and linked with the new auto attendant. -->
 
> [!TIP]
> 若要將來電重新導向給以電話系統授權為線上使用者的操作員或功能表選項，您必須啟用企業語音。 請參閱[指派商務用 Skype 授權](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses)或[指派 Microsoft 團隊授權](assign-teams-licenses.md)。 您也可以使用 Windows PowerShell。 例如，執行：`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

## <a name="step-2--create-auto-attendants"></a>步驟2：建立自動語音應答

> [!IMPORTANT]
> 每個自動語音應答都必須有一個相關聯的[資源帳戶](manage-resource-accounts.md)。 您必須先建立資源帳戶，然後才能將它與自動語音應答建立關聯。

### <a name="with-the-microsoft-teams-admin-center"></a>使用 Microsoft 團隊系統管理中心

在**Microsoft [團隊管理中心**] 中，按一下 [**語音** > **自動**語音應答]，然後按一下 [ **+ 新增**]：

#### <a name="general-info-page"></a>一般資訊頁面

![[我的自動助理] 頁面的螢幕擷取畫面](media/edacec94-9384-4a87-be0a-5c49a151287e.png)

* * *

![數位1的圖示，前一個螢幕擷取畫面](media/teamscallout1.png)
**名稱**中的標注輸入自動語音應答的顯示名稱。 名稱是必要的，而且最多可以包含64個字元，包括空格。 您在此處指定的**名稱**會列在 [**自動**語音應答] 索引標籤的欄中。

<a name="phonenumber"> </a>

* * *

![數位2的圖示，前一個螢幕擷取畫面](media/teamscallout2.png)
 <a name="operator"></a> 
**操作員**中的標注這是選擇性的（但建議使用）。 您可以設定 [**運算子**] 選項，讓呼叫者中斷功能表並向指定的人朗讀。

預設會將0按鍵指派給接線員。

如果您設定一個運算子，請在 [**通話流程**] 頁面上的 [**編輯] 功能表選項**中，告訴給有關該選項的人員。 如果您在自動語音應答上設定操作員，您可以在 [**呼叫者會聽到**] 方塊中輸入對應的提示文字，或變更您的音訊檔案，以包含此選項。 例如，"For 運算子，請按零。

您有幾種方式可以設定運算子：

- [**無] 運算子**會停用「運算子」和「按0」選項。 這是目前的預設值。
- **貴組織中的人員**會為 Office 365 中已啟用企業語音或指派通話方案的電話系統授權指派人員。 您也可以將呼叫者設定為傳送給語音信箱。 若要傳送來電者至語音信箱，請選取**貴組織中的人員**，並將該帳戶的設定設為直接傳送來電給語音信箱。

     > [!Note]
     > **貴組織中的人員**可以是線上使用者，或使用商務用 Skype Server 託管內部部署的使用者。

- **語音應用程式** 選取連結到已建立之自動語音應答或通話佇列之資源帳戶的名稱。 要求操作員的呼叫者會被重新導向。  
<!--   

- **Auto attendant** Select the name of the resource account linked to an auto attendant that has already been created. Callers that request an operator are redirected there.
- **Call queue** Select the name of the resource account linked to a call queue that has already been created. Callers that request an operator are redirected there.

**Phone number (optional)** Enter the service phone number you want to assign to the new resource account this wizard creates and links to the new auto attendant. If you intend this auto attendant to be a nested auto attendant, it doesn't need a phone number. You can add one if for some reason you require several ways to connect to the auto attendant system.

> [!NOTE]
> Auto attendants created after October 10th, 2019 also create a new [resource account](manage-resource-accounts.md) that is associated with the auto attendant. If a phone number is applied to the auto attendant's resource account,  a Phone System - Virtual user license is applied to the resource account if one is available.
-->

* * *

<a name="timezone"> </a>

![數位3的圖示，前一個螢幕擷取畫面](media/teamscallout3.png) **時區**中的標注，您必須為自動語音應答設定時區。 此設定可以與您組織的主要位址時區，或其他時區相同。 每個自動助理都可以有不同的時區。 自動語音應答的 [上班時間] 設定也會使用 [此時區]。

* * *

![數位4的圖示，前一個螢幕擷取畫面](media/teamscallout4.png)
 <a name="language"></a> 
**語言**中的標注選取您要用於自動語音應答的語言。 自動語音應答會將該語言用於呼叫者，且系統會以這種語言來播放所有系統提示。

 * * *

![# 5 的圖示，在選取此選項時，前](media/teamscallout5.png)
一個螢幕擷取畫面中的標注會**啟用語音輸入**語音辨識功能。 呼叫者可以使用[您所設定之語言](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)的語音輸入。 如果您只想讓其他人使用電話鍵進行選取，您可以將語音辨識設定為 [**關閉**]。

* * *  

完成選取後，請按 **[下一步**]。

#### <a name="call-flow"></a>通話流程

<a name="greetingsandrouting"> </a>

> [!TIP]
> 您可以選擇設定自訂的上班時間排程，並在上班時間期間和之後進行不同的通話流程行為。 若要設定自訂排程，請設定[下班後的選擇性通話流程](#call-flow-for-after-hours)。 根據預設，自動語音應答會使用上班時間通話流程。

您可以設定自訂的問候語、提示及功能表，讓使用者在到達您的自動語音時聽到。

![螢幕擷取畫面： [呼叫處理] 頁面問候區段](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)

* * *

**第一次播放問候訊息**問候語是選擇性的，可以設定為 [**沒有問候語**]、[**播放音訊**檔] 或 [**輸入問候] 訊息**。

> [!NOTE]
> 對第一層自動語音應答而言，問候非常重要。 嵌套的自動語音助手通常不需要問候語。

![數位1的圖示，前一個螢幕擷取畫面](media/teamscallout1.png)中的標注如果您選取 [**沒有問候語**]，來電程式在由您稍後選取的其中一個動作前，就沒有聽到訊息或問候語。 

<!-- You can also upload an audio file (in .wav, mp3 or .wma formats), or create a custom greeting using Text-to-Speech.-->

![數位2的圖示，前一個螢幕擷取畫面](media/teamscallout2.png)中的標注如果您選取 [**播放音訊**檔]，您可以使用 [**上傳**檔案] 按鈕上傳儲存為音訊的錄製問候語訊息。WAV，。[MP3] 或。WMA 格式。 錄製不能大於 5 MB。

![數位3的圖示，前一個螢幕擷取畫面](media/teamscallout3.png)中的標注輸入**問候訊息**：如果您選擇這個選項，請在提供的欄位中輸入您想要系統讀取的文字（最多1000個字元）。 例如，輸入「歡迎使用 Contoso。 您的通話對我們很重要。」 [輸出] 是由文字到語音軟體所建立。

* * *

您可以在 [從下列動作**傳送通話**] 區段中，選取 [呼叫] 旁的選項。 設定為 **[中斷連線]、[** 重新**導向通話**] 或 [**播放] 功能表選項**。

如果您選取 **[中斷連線]**，則會在問候語播放之後中斷呼叫者的連線。 

<a name="redirectcalls"> </a>

![數位4的圖示，前一個螢幕擷取畫面](media/teamscallout4.png)中的標注會重新**導向呼叫**將來電者傳送給所選的目的地，而不需選擇 [從選項]。 可能的設定為：

  - **組織中的人員**您選擇的帳戶必須具備企業語音的電話系統授權，或是在 Office 365 中有已指派的通話方案。 您可以將其設定為將呼叫者傳送至語音信箱：選取 [**組織中的人員**]，然後將該帳戶設定為 [讓來電直接轉接至語音信箱]。

  > [!Note]
  > **組織中的人員**可以是線上使用者，或使用商務用 Skype Server 託管內部部署的使用者。

  - **語音應用程式**選取已設定的自動語音應答或通話佇列。 您可以依與服務相關聯之資源帳戶的名稱來搜尋自動語音應答或通話佇列。

<!-- - **Auto attendant** Select the name of an existing auto attendant.
- **Call queue** Select the name of an auto attendant that has already been created.
- **External phone number** routes the caller to a phone number outside your local system.
- **Operator** directs the call to a user you designate as an Operator. If you haven't previously set up an operator, an option to create one now shows up. The 0 key is assigned to Operator by default. Options for setting an Operator are:

  - **No operator** disables the "Operator" and "Press 0" options.
  - **Person in your organization** can be an Online user or a user hosted on-premises using Skype for Business Server. They must have a Phone System license that is enabled for Enterprise Voice or assigned Calling Plans in Office 365. Search for the operator in the **Destination for your operator** field.
  - **Auto attendant** lets you choose the name of an existing auto attendant.
  - **Call queue** lets you select an existing call queue.
  - **Group Voicemail** routes the call to a voicemail box that you select. -->

 * * *

![螢幕擷取畫面： [呼叫處理頁面動作] 區段](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8b.png)

![數位1的圖示，當您選取 [**播放] 功能表選項**時，在先前的螢幕擷取畫面](media/teamscallout1.png)中，您可以選取是使用音訊檔案，還是要將轉譯成文字的文字轉換成語音，以向呼叫者提供撥號鍵台功能表選項。 選取此選項，而不是 [重新**導向呼叫** **] 或 [中斷連線]** 選項。


![數位2的圖示，前一個螢幕擷取畫面](media/teamscallout2.png)中的標注會**播放音訊**檔，讓您設定來電者選擇的提示和選項。 
- 如果您選取 [**播放音訊**檔]，您可以使用 [**上傳**檔案] 按鈕，上傳儲存為音訊的錄製問候語訊息。WAV，。[MP3] 或。WMA 格式。 錄製不能大於 5 MB。

- **輸入問候訊息**如果您選擇此選項，請在提供的欄位中輸入您想要系統讀取的文字（最多1000個字元）。 例如，輸入「歡迎使用 Contoso。 您的通話對我們很重要。」 [輸出] 是由文字到語音軟體所建立。

[**設定] 功能表選項**您可以在此對話方塊中新增或移除電話鍵台或語音命令。 若要刪除功能表選項，請移除語音命令專案，然後將 [重新**導向**] 設定為 [返回] 進行**選取**。

> [!TIP]
> 更新功能表提示文字，或在移除選項時重新錄製音訊提示。 為呼叫者播放的功能表提示不會自動更新。  
>
> 任何順序都可以新增或移除任何功能表選項，而且鍵對應不一定是連續的。 例如，您可以建立一個含有鍵0、1和3的功能表，並對應至選項，而不使用鍵2。

> [!NOTE]
> 按鍵\* （重複）及\# （背面）是由系統所保留，而且無法重新指派。 如果已啟用語音辨識功能，按下 * 將與 "Repeat" 相對應，且 # 會與 "Back" 聲音命令相對應。

![數位3的圖示，前一個螢幕擷取畫面](media/teamscallout3.png)中的標注若要設定功能表選項，請按一下 [ **+ 指派撥號鍵**]，然後輸入下列選項的資訊：

![數位4的圖示，在前一個螢幕擷取畫面](media/teamscallout4.png)中的 [語音]**命令**欄中，選項最多可包含64個字元，而且可以包含多個字，例如「客戶服務」或「作業與使用中」。   如果已啟用語音辨識功能，系統會自動辨識名稱，而且呼叫者可以按3、說「三」，或者說「客戶服務」，選取對應至鍵3的選項。 此文字也會由針對服務確認提示的文字轉換語音，這可能是「將您的通話轉移到操作員」之類的內容。

![數位5的圖示，前一個螢幕擷取畫面](media/teamscallout5.png)中的標注： [**重定向至**] 選項會在您按下對應的按鍵時，或使用語音辨識選取選項時，進行呼叫的位置。 通話可以傳送至：

<!-- Is the Operator behavior changing here? Looks like operator is only an available option for dial key 0 -->

- **運算子**如果已設定操作員，該選項會自動對應到 key 0，但是也可以刪除或重新指派給不同的金鑰。 選取此選項的來電者會傳送至指定的操作員。 如果運算子未設為任何鍵，語音命令 "Operator" 也會停用。 
- **組織中的人員**可以是線上使用者，或使用商務用 Skype Server 託管內部部署的使用者。 使用者必須具備在 Office 365 中啟用企業語音或指派通話方案的電話系統授權。 在 [**依名稱搜尋**] 欄位中搜尋人員。

  - **語音應用程式**選取已設定的自動語音應答或通話佇列。 您可以依與應用程式相關聯之資源帳戶的名稱來搜尋自動語音應答或通話佇列。

<!-- - **Auto attendant** Select the name of an existing auto attendant in the **Search by name** field. You will also have to select a resource account associated to the auto attendant. The caller who selects this option is sent to that auto attendant.
- **Call queue** Select the name of an existing call queue in the **Search by name** field. You will also have to select a resource account associated to the call queue. The caller who selects this option is sent to that call queue, where the call is answered by a call agent.
- **External phone number** routes the caller to a designated phone number outside your local system.<!-- does this have prerequisites like direct routing?
- **Group Voicemail** routes the call to a voicemail box that you select.  -->

![數位6的圖示，在此區段的前一個螢幕](media/teamscallout6.png)快照**目錄搜尋**中，您可以啟用 [透過**名稱撥號**]，並以 [撥打自動語音應答的**方式撥號**] 進行撥號。   您可以在 [選用的撥號作用域] 頁面中，設定這些服務中和不包含的人員。 [目錄搜尋] 預設會設定為 [**無**]。

**依名稱撥號**如果您啟用這個選項，來電者就可以使用 [透過**名稱撥號**] 搜尋貴組織中的人員。 他們會說出使用者的名稱和語音辨識會與使用者相符。 您可以在 [選用的撥號作用域] 頁面中，設定這些服務中和不包含的人員。 使用電話系統授權的任何線上使用者，或任何使用商務用 Skype Server 主機內部部署的使用者，都是合格的使用者，而且可以使用 [撥號者名稱] 找到。

[!INCLUDE [preview-feature](includes/preview-feature.md)]

透過**延伸撥號**（此預覽功能尚未提供給 [一般公用]）如果您啟用此選項，則呼叫者可以輸入其電話分機，與貴組織中的使用者連線。 您可以在 [選用撥號作用中] 頁面中，選取哪些使用者列為 [可供**撥號**] 或 [無法使用]。 使用電話系統授權的任何線上使用者，或任何使用商務用 Skype Server 主機內部部署的使用者，都是符合資格的使用者，而且可透過分機找到。

> [!IMPORTANT]
> 請注意下列事項：
>- 您想要讓撥打電話的使用者在[Microsoft 365 系統管理中心](https://docs.microsoft.com/office365/admin/add-users/add-users?view=o365-worldwide#use-the-new-admin-center-to-add-users)指派的電話號碼或行動電話號碼的一部分，必須具備副檔名。  在 [使用者電話號碼] 欄位中輸入延伸所需的格式，可以`+<phonenumber>;ext=<extension>`是`x<extension>`或。
>- 目前不支援在團隊系統管理中心指派延伸。 您必須使用[MsolUser](https://docs.microsoft.com/powershell/module/msonline/set-msoluser?view=azureadps-1.0) powershell 命令或 Microsoft 365 系統管理中心。
>- 在 AAD PhoneNumber 和 MobilePhone 屬性的變更可供使用前，可能需要最多12小時的時間。
>- 請不要定義使用者 LineUri 的延伸。 目前不支援這種情況。
>- 自動語音應答可以設定為透過名稱撥號，或使用撥打電話給撥號，但不能同時使用這兩者。

> [!NOTE]
> 如果您想要同時使用 [透過**名稱撥號**]**和 [透過撥號撥打**] 功能，您可以建立主要自動語音應答（透過**名稱撥號**），提示呼叫者選擇功能表選項（如果他們知道使用者的副檔名），並將該選項設定為將來電轉接到已啟用 [透過電話撥打電話] 的自動語音應答。

* * *

<!--
**Instructions for callers** lets you choose **Use recorded call instructions** or **Write your call instructions**.  

If you choose **Use recorded call instructions**, you have the option to record and upload new or prerecorded sound files to play as menu instructions. The same app used in recording the auto attendant greeting is used here.

If you choose **Write your call instructions**, enter the script  you want the system to read (up to 1000 characters). For example, you might enter text that begins "Please choose from one of the following menu options ... " and provide a script written to reflect your configuration.
* * *  -->

當您完成選取專案時，如果您想要變更高級設定，請按一下 **[下一步]** ，如果您想要使用預設設定，請按一下 [**提交**] （例如：
- 下班時間的通話流程
- 假日的通話流程
- 撥號作用中
- 資源帳戶

由於您必須具備自動語音應答才能擁有資源帳戶，因此您可以選擇繼續至 [**資源帳戶**] 頁面，並關聯您已設定的資源帳戶，或建立資源帳戶並將其與自動關聯在[Microsoft 團隊中的 [管理資源帳戶](manage-resource-accounts.md)] 中所述的 [助理]。 您將無法使用此自動語音應答，除非它已與資源帳戶相關聯。 若要這樣做，請按一下畫面底部的 **[下一步]** 按鈕，然後按一下左側導覽中的 [**資源帳戶**]，即可直接移至 [資源帳戶] 頁面，並將您的自動助手與資源帳戶建立關聯。

#### <a name="advanced-settings-optional"></a>[高級設定] （選用）

您可以在四個額外的螢幕上設定或保留您選擇的預設值。

##### <a name="call-flow-for-after-hours"></a>下班時間的通話流程

根據預設，自動語音應答的上班時間設定為上午9點，星期一到星期五  <!--24/7-->，且停用*下班時間之後*的通話流程選項，因為所有的時間都被視為「*上班時間*」。 當您選取 [**設定自訂工作時間**] 選項時，[**下班時間之後的通話流程**] 頁面會設定自動回應在下班後所使用的通話處理規則。 可用的選項是相同的，而差異就是為不同的功能表和行為設定排程的能力。

自動語音應答的系統可能只需要設定第一層自動語音應答的下班時間呼叫處理行為。 嵌套式自動語音應答甚至可能無法由第一層自動語音應答呼叫，但系統可以為它所使用的每個自動語音應答定義時間（以時間為單位）行為。

從最初起，上班時間定義為從 12:00 am 開始，到 12:00 pm，從星期日到星期六結束。 在上班時間以外的所有時間，都是*在下班後*。


![[下班後通話流程] 設定的螢幕擷取畫面](media/aa-afterhour.png)
 * * *

![數位1的圖示，在前一個螢幕擷取畫面](media/teamscallout1.png)中，您可以按一下 [**選取 24/7** ]，以完成此自動語音應答的所有上班時間。

![數位2的圖示，前一個螢幕擷取畫面](media/teamscallout2.png)中的標注選取 [**重設為預設值**] 選項，以還原排程中的所有變更，並傳回 9:00 am 到 5:00 pm 的預設定義（星期一到星期五）。

![數位3的圖示，前一個螢幕擷取畫面](media/teamscallout3.png)中的標注選取 [**清除所有時間**] 來完全清除排程。 我們不建議您選取此選項並保留未設的時間，因此請只在您想要完全重新執行工作時間時才使用這個選項。

![數位4的圖示（編號5的前一個螢幕擷取畫面](media/teamscallout4.png)  ![圖示中的標注），前一個螢幕擷取畫面](media/teamscallout5.png)中的標注可自訂周中某天的開始或結束時間，請按一下您想要重設的 [**開始**] 或 [**結束**] 時間，然後從顯示的清單中選取新的時間。 此清單可讓您以15分鐘的間隔來選取 [上班時間]，而您在此選取的上班時間是以您在 [**一般資訊**] 頁面上所設定的時區為基礎。

 <!-- The **Apply to all days** option can be used to reset all days of the week to match the settings for that day. This makes setting weekdays and weekends to different hours easier.-->

![數位6的圖示，前一個螢幕擷取畫面](media/teamscallout6.png)中的標注若要設定工間休息（例如午餐），請選取 [新增**時間**]，以建立新的表格列，然後選取 [新的開始] 和 [結束] 時間。 您可以在上班時間內設定多個工間休息。

下班時間之後所提供的[通話流程](#call-flow)選項，與在上班時間期間提供的選項相同。 向下滾動 [資訊輸入] 頁面，設定 [下班後通話流程] 選項。

* * *

當您完成選取專案時，請按 **[下一步]**。 您也可以按一下左側導覽中的 [**資源帳戶**]，直接移至 [資源帳戶] 頁面，並將您的自動語音助理與資源帳戶相關聯。

##### <a name="call-flow-during-holidays"></a>假日期間的通話流程

<a name="holidaygreetings"> </a>

您最多可以將20個排定的假日新增至每個自動語音應答。 您的組織可能已經定義了假日，如在[Microsoft 團隊中設定假日](set-up-holidays-in-teams.md)中所述。 如果不是，您會看到下列畫面： 

![螢幕擷取畫面：未設定假日](media/aa-no-holidays.png)

![數位1的圖示，前一個螢幕擷取畫面](media/teamscallout1.png)中的標注，在自動語音應答中設定假日的自訂通話流程，按一下 [ **+** 新增] [查看**新假日通話流程**] 畫面。
> [!TIP]
> 若要建立假日，您可以在**組織內設定** > **假日**移至畫面上。  



![螢幕擷取畫面：新增通話處理常式](media/50a5ce88-7f39-4210-808a-da7ced969854b.png)

* * *

![數位1的圖示，前一個螢幕擷取畫面](media/teamscallout1.png)中的標注會輸入新通話流程的**名稱**。

![數位2的圖示，前一個螢幕擷取畫面](media/teamscallout2.png)中的標注如果您已建立假日，您會在 [**假日**] 下拉式功能表中看到這些專案，然後加以選取。 您可能會看到一個未使用的選項，您可以在需要的情況中進行編輯。 如果不是，請按一下下拉式清單底部的 [**新增**]，以建立新的假日。  如需建立假日的步驟，請參閱[在 Microsoft 團隊中設定假日](set-up-holidays-in-teams.md)。 

假日通話流程名稱最多可以有64個字元，且對於組織而言必須是唯一的。 例如，在同一個組織中，您無法將兩個假期通話流程命名為「感恩節」。 您的自動語音應答可以針對您設定的每個假日進行通話流程，但您可能會想要在自訂的問候語以外的一組常見行為中進行。

![數位3的圖示，前一個螢幕擷取畫面](media/teamscallout3.png)中的標注：假日通話流程的[問候](#call-flow)選項與上班時間內提供的選項相同。 在播放問候語之後所執行的**動作**也類似，只是在您唯一可用的動作是 **[中斷連線]** 或 [重新**導向**]，以及選擇 [**重定向至**] 選項時，操作員不是其中一個可用的選項. 您無法設定假日流程專用的功能表。

> [!NOTE]
> 根據預設，在假日期間收到的所有來電都設定為在問候語（如果有的話）之後**中斷**連線，因此，如果您想要自訂行為，您必須指定重新導向。

![[假日] 頁面中通話流程的螢幕擷取畫面](media/50a5ce88-7f39-4210-808a-da7ced969854.png)

按一下 [儲存] 以完成假日通話流程的建立。 在您建立假日通話流程之後，它會顯示在 [假日] 畫面的**通話流程中**。

按一下 [設定撥號作用中 **]、[** **返回**]，然後在經過一個小時的通話流程之後進行變更，並在完成後**提交**。 您也可以按一下左側導覽中的 [**資源帳戶**]，直接移至 [資源帳戶] 頁面，並將您的自動語音助理與資源帳戶相關聯。

#### <a name="dial-scope"></a>撥號作用中

<a name="dialscope"> </a>

![顯示 [撥號作用中] 頁面的螢幕擷取畫面](media/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)

在此頁面上，您可以設定您的目錄中所列的人員，並在人員呼叫您的組織時可使用 [撥號]。 [依名稱撥號] 預設會在先前的畫面中設為 [**關閉**]。 如果您先前選取了 [透過**撥號撥打**]，就可以使用副檔名為 [所有] 的使用者。

![數位1的圖示，前面螢幕](media/teamscallout1.png)快照中的標注包括本區段中的選項，**包括****所有線上使用者**或**自訂使用者群組**

如果您選取 [**所有線上使用者**]，所有符合資格的使用者都會包含在目錄搜尋中。

**自訂使用者群組**這個選項可讓您搜尋並選取您組織中已建立的 Office 365 群組、通訊群組清單或安全性群組。 如果使用者位於所選的 Office 365 群組、通訊群組清單或安全群組中，而且他們是使用**電話系統授權的線上使用者**，或是使用商務用 Skype Server 主機內部部署的使用者，就會新增到目錄中。 您可以將多個 Office 365 群組、通訊群組清單和安全性群組新增到目錄中。

<a name="dialscope"> </a>

在此頁面上，您可以設定貴組織中的哪些使用者會列在您的目錄中，並可在撥入您組織的人員時，透過名稱撥號。

![數位2的圖示，前一個螢幕擷取畫面](media/teamscallout2.png)中的標注會**排除**此區段中的選項，讓您可以從組織的目錄中排除特定使用者或使用者群組。

如果您選取 [**無**]，所有符合資格的使用者都會包含在目錄搜尋中。

**自訂使用者群組**您可以搜尋已在貴組織中建立的 Office 365 群組、通訊群組清單或安全性群組。 該群組中的使用者會從 [目錄搜尋] 中排除。 您可以新增多個 Office 365 群組、通訊群組清單和安全性群組。


如果啟用 [依名稱撥號] 時，系統會將設定保留為預設值，則所有符合資格的使用者都會包含在目錄搜尋中。

> [!NOTE]
> 最多可能需要36小時，才能讓新使用者將其名稱列在目錄中。 當有人使用 [透過名稱撥打撥號] 語音辨識時，可能無法使用此功能的新帳戶。

輸入所有必要的欄位並設定 [呼叫處理] 功能表和選項之後，請按 **[下一步]** 以繼續關聯資源帳戶。

#### <a name="resource-accounts"></a>資源帳戶

所有自動語音應答都必須有關聯的資源帳戶。  第一層自動語音應答絕對必須至少有一個資源帳戶有關聯的服務號碼。 如果您想要的話，您可以將多個資源帳戶指派給自動語音應答，每個都有不同的服務號碼。

如果您尚未將資源帳戶設定為自動語音應答，您會看到下列畫面： 

![螢幕擷取畫面：選用資源帳戶管理](media/aa-ra-optional.png) 

![數位1的圖示，前一個螢幕擷取畫面](media/teamscallout1.png)中的標注若要將一或多個現有且未分派的資源帳戶新增到自動語音應答，請按一下 [**新增帳戶**]，然後從提供的對話方塊中選取它們。

![新的 [助理摘要] 視圖的螢幕擷取畫面](media/aa-assigned.png)

![數位1的圖示，前一個螢幕擷取畫面](media/teamscallout1.png)中的標注若要新增額外的資源帳戶，請按一下 [ **+ 新增帳戶**]。

![數位2的圖示，前一個螢幕擷取畫面中有一個標注](media/teamscallout2.png) 指派給此自動語音應答的資源帳戶或帳戶會顯示在清單中。

## <a name="edit-auto-attendants"></a>編輯自動語音應答

儲存新的自動語音應答之後，它會列在 [**自動**語音應答] 頁面上。 此頁面可讓您快速查看已設定的部分選項，包括名稱、相關聯的資源帳戶、語言及已指派的操作員。

![[助理] 清單的螢幕擷取畫面](media/aa-list.png)

如果您想要變更自動助理設定，請選取自動語音應答，然後在 [動作] 窗格中按一下 [**編輯**]。

<!-- To quickly place a test call to your auto attendant, click the **Test** button in the Action pane. -->

<!-- ## Summary view

You can use the Summary page to review the settings you've created.

![screenshot of the new attendant summary view](media/aa-new-summary.png)

Press the **Create** button to finish setup of your new auto attendant. -->

### <a name="create-an-auto-attendant-with-powershell"></a>使用 Powershell 建立自動助理

您也可以使用 PowerShell 來建立及設定自動語音應答。 以下是您需要管理自動語音應答的 Cmdlet：

- [新-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant?view=skype-ps)  
- [Set-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant?view=skype-ps)
- [CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant?view=skype-ps)
- [CsAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays?view=skype-ps)
- [移除-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant?view=skype-ps)
- [新-CsAutoAttendantMenu](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu?view=skype-ps)
- [新-CsOnlineAudioFile](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile?view=skype-ps)
- [新-CsAutoAttendantCallFlow](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow?view=skype-ps)
- [Export-CsAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays?view=skype-ps)
- [新-CsOnlineTimeRange](https://docs.microsoft.com/powershell/module/skype/new-csonlinetimerange?view=skype-ps)
- [新-CsOnlineDateTimeRange](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps)
- [新-CsOnlineSchedule](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule?view=skype-ps)
- [CsAutoAttendantSupportedTimeZone](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone?view=skype-ps)
- [新-CsAutoAttendantCallHandlingAssociation](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation?view=skype-ps)
- [CsAutoAttendantSupportedLanguage](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage?view=skype-ps)
- [匯入-CsAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays?view=skype-ps)
- [新-CsAutoAttendantCallableEntity](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity?view=skype-ps)

### <a name="more-about-windows-powershell"></a>深入瞭解 Windows PowerShell

- Windows PowerShell 全部說明如何管理使用者，以及允許或不允許的使用者執行。 在 Windows PowerShell 中，您可以從單一管理點管理 Office 365 和 Microsoft 團隊，以簡化日常作業。 若要開始使用 Windows PowerShell，請參閱以下主題：

  - [Windows PowerShell 與 Lync Online 的簡介](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [為什麼需要使用 Office 365 PowerShell](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- Windows PowerShell 的速度、簡潔性和生產率都有許多優點，只是使用 Microsoft 365 系統管理中心，例如一次為多個使用者進行設定變更。 請參閱下列主題，瞭解這些優點：

  - [使用 Office 365 PowerShell 管理 Office 365](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [使用 Windows PowerShell 管理商務用 Skype Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a>相關主題

[以下是您在 Office 365 中使用電話系統所取得的結果](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[取得服務電話號碼](/microsoftteams/getting-service-phone-numbers)

[音訊會議與通話方案的適用國家/地區](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[新-CsOrganizationalAutoAttendant](https://docs.microsoft.com/en-us/powershell/module/skype/new-csorganizationalautoattendant?view=skype-ps)  

[什麼是雲端自動語音應答？](what-are-phone-system-auto-attendants.md)

[小型企業範例-設定自動助手](/microsoftteams/tutorial-org-aa)  
