---
title: 設定 Teams 會議並保護高度機密資料
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
audience: admin
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- m365solution-compliantmeetings
- m365initiative-meetings
- highpri
appliesto:
- Microsoft Teams
description: 瞭解如何使用範本和敏感度標籤，設定 Teams 會議以保護高度機密資訊。
ms.openlocfilehash: 0d49cc4305f77b4b4208cc0f7418d5506155d0d6
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/13/2023
ms.locfileid: "69800260"
---
# <a name="configure-teams-meetings-with-protection-for-highly-sensitive-data"></a>設定 Teams 會議並保護高度機密資料

[!INCLUDE[Teams Premium ECM](includes/teams-premium-ecm.md)]

針對 *高度機密* 的保護層級，我們將會查看兩種不同的案例：
- 出席者參與並與簡報者互動的高度機密會議
- 出席者無法互動且只是檢視簡報的高度機密簡報

> [!Note]
> 敏感度標籤和自訂會議範本中的會議設定需要Teams 進階版。

#### <a name="highly-sensitive-meetings"></a>高度機密的會議

對於高度機密的會議，我們會限制誰可以略過大廳、誰可以簡報、參與者可以聊天，而且我們會封鎖從會議聊天複製的內容。 我們也會針對共用視訊和內容啟用端對端加密及浮水印。 因為我們使用浮水印，會議錄製將會停用。

下表說明我們將針對高度敏感性的會議限制哪些動作，以及設定這些設定的位置。

|功能|設定|位置|執行|
|:------|:------|:-------|:-------|
|允許出席者使用相機|**開啟**|範本|否|
|允許出席者使用麥克風|**開啟**|範本|否|
|將浮水印套用至每個人的視訊摘要|**開啟**|標籤|是|
|將浮水印套用至共用內容|**開啟**|標籤|是|
|端對端加密|**開啟**|標籤|是|
|管理出席者看到的內容|**開啟**|範本|是|
|會議聊天|**僅限會議**|範本|是|
|撥入人員可以略過大廳|**關閉**|標籤|是|
|防止將聊天內容複寫到剪貼簿|**開啟**|標籤|是|
|自動錄製| (因為浮水印和加密) 而停用|不適用|不適用|
|誰可以略過大廳|**僅限召集人和共同召集人**|標籤|是|
|誰可以簡報|**僅限召集人和共同召集人**|標籤|是|
|誰可以錄製| (因為浮水印和加密) 而停用|不適用|不適用|

敏感度標籤或會議範本會強制執行列為強制執行的設定。 會議召集人可以變更未強制執行的設定。

#### <a name="highly-sensitive-presentations"></a>高度敏感的簡報

對於高度機密的簡報，如果不希望與會議出席者互動，我們會關閉出席者的麥克風和攝影機，並關閉會議聊天。

如果您想要允許出席者詢問簡報者的問題，會議召集人可以開啟 Q&A 功能。  (在 Teams 系統管理會議原則中確定已啟用此功能。) 

下表說明我們將針對高度敏感性的簡報限制哪些動作，以及設定這些設定的位置。

|功能|設定|位置|執行|
|:------|:------|:-------|:-------|
|允許出席者使用相機|**關閉**|範本|是|
|允許出席者使用麥克風|**關閉**|範本|是|
|將浮水印套用至每個人的視訊摘要|**開啟**|標籤|是|
|將浮水印套用至共用內容|**開啟**|標籤|是|
|端對端加密|**開啟**|標籤|是|
|管理出席者看到的內容|**開啟**|範本|是|
|會議聊天|**關閉**|範本|是|
|撥入人員可以略過大廳|**關閉**|標籤|是|
|防止將聊天內容複寫到剪貼簿|**開啟**|標籤|是|
|自動錄製| (因為浮水印和加密) 而停用|不適用|不適用|
|誰可以略過大廳|**僅限召集人和共同召集人**|標籤|是|
|誰可以簡報|**僅限召集人和共同召集人**|標籤|是|
|誰可以錄製| (因為浮水印和加密) 而停用|不適用|不適用|

敏感度標籤或會議範本會強制執行列為強制執行的設定。 會議召集人可以變更未強制執行的設定。

## <a name="options-for-recording-meetings"></a>錄製會議的選項

針對 *高度機密* 的保護層級，我們會針對會議和簡報使用浮水印和端對端加密。 不過，使用這些功能可防止錄製會議。 如果您需要錄製高度機密的會議，建議您不要將浮水印和端對端加密設定為敏感度標籤的一部分。 會議召集人仍然可以使用這些專案來記錄他們不需要錄製的會議。

## <a name="presentation-options-for-highly-sensitive-meetings"></a>高機密會議的簡報選項

針對 *高度敏感性的* 會議，我們會針對誰可以發表簡報，以及內容的共用方式強制執行特定設定。

藉由開啟 **[管理出席者可以看到的內容**]，我們確保會議召集人可以先檢查共用內容，再將內容帶入螢幕供參與者使用。 在此範例中，我們使用範本預設開啟此功能，但您也可以視需要在範本中強制執行此動作。

藉由在敏感度標籤中將 [**只有召集人] 和 [共同召集** 人] 進行 **簡報**，我們確保只有會議召集人才會出席。

## <a name="lobby-options-for-sensitive-meetings"></a>敏感性會議的大廳選項

我們會使用敏感度標籤，防止會議召集人以外的任何人略過大廳。 這可讓召集人檢查每位出席者，並確保應該允許他們參加。

## <a name="participation-options-for-highly-sensitive-meetings"></a>高度機密會議的參與選項

雖然可以使用敏感度標籤控制聊天，但在這個案例中我們會使用範本，讓會議和簡報範本可以共用相同的標籤。 我們會針對會議將聊天限制為僅限會議，並針對簡報完全關閉聊天功能。  (召集人可以在簡報中使用 Q&A 功能，允許觀眾提出批註或問題。) 

對於會議和簡報，我們也會防止將聊天內容複寫到剪貼簿。

當我們將出席者麥克風和相機保留為會議啟用狀態時，我們會針對簡報關閉這些麥克風和攝影機。

## <a name="sensitivity-labels"></a>敏感度標籤

針對敏感性保護層級，我們將使用敏感度標籤，讓您直接在會議或會議範本中使用。 根據您選擇的設定而定，這個標籤也可以用來將小組和個別檔案分類。

如果您已在組織中部署敏感度標籤，請考慮此標籤如何符合您整體標籤策略。 如有需要，您可以變更名稱或設定，以符合貴組織的需求。 如果您已經有用於機密資訊的標籤，您可以編輯標籤並將 Teams 會議新增至其中。

> [!IMPORTANT]
> 如果限制從聊天複製的敏感度標籤在容器標籤中指定為預設頻道標籤，則具有該容器標籤的團隊將會限制團隊中所有頻道在頻道會議內外的聊天複製。

建立敏感度標籤
1. 開啟[Microsoft Purview 合規性入口網站](https://compliance.microsoft.com)。
1. 在 [ **解決方案]** 底下，按一下 **[資訊保護]**。
1. 按一下 **[建立標籤]**。
1. 為標籤命名。 我們建議 **使用高度敏感性**，但如果該名稱已在使用中，您可以選擇不同的名稱。
1. 新增顯示名稱和描述，然後按 [ **下一步]**。
1. 在 [ **定義此標籤的範圍** ] 頁面上，選取 [ **專案** ] 和 [ **包含會議]**。  (請注意，如果您要將此標籤用於其他用途，可以選取其他選項。) 
1. 選取 **[下一步]**。
1. 繼續選取您要搭配此標籤使用的選項，然後在 **[Teams 會議和聊天** 的設定] 頁面上，選擇下列值：
    1. 選 **取 [控制誰可以略過大廳** ]，然後從下拉式清單中選取 **[只有召集人和共同召集** 人]。
    1. 確定取消核取 **[允許撥入使用者略過大廳]**
    1. 選 **取 [控制誰可以簡報** ]，然後從下拉式清單中選取 **[只有召集人和共同召集** 人]。
    1. 選 **取 [控制會議視訊和音訊的端對端加密** ]，然後將端 **對端加密** 設定為 [ **開啟]**。
    1. 選 **取 [控制浮水印** ]，然後設定 [ **將浮水印套用至共用內容** ]，並將 **浮水印套用至每個人的視訊摘要** 至 **[開啟]**。
    1. 選取 **[防止將聊天內容複寫到剪貼簿]**。
    1. 設定貴組織所需的任何其他設定。
    <!--:::image type="content" source="media/teams-meeting-sensitivity-label-highly-sensitive-small.png" alt-text="Screenshot of sensitivity label meeting settings." lightbox="media/teams-meeting-sensitivity-label-highly-sensitive-large.png":::-->
1. 選取 **[下一步]**。
1. 使用您要使用的任何其他設定完成精靈，然後選取 [ **建立標籤**]，然後選取 [ **完成]**。

建立標籤之後，您必須將標籤發佈給使用標籤的使用者。 為了獲得高度機密性保護，我們會將標籤提供給所有使用者使用。 您會在 [**資訊保護**] 頁面的 [**卷** 標原則] 索引標籤Microsoft Purview 合規性入口網站中發佈標籤。 如果您有適用于所有使用者的現有原則，請將此標籤新增至該原則。 如果您需要建立新原則，請參閱 [建立標籤原則以發佈敏感度標籤](/compliance/create-sensitivity-labels#publish-sensitivity-labels-by-creating-a-label-policy)。

如需有關在會議中使用敏感度標籤的其他資訊，請參閱 [使用敏感度標籤來保護行事曆專案、Teams 會議和聊天](/microsoft-365/compliance/sensitivity-labels-meetings)。

## <a name="meeting-templates"></a>會議範本

在 *高度機密* 的保護層級中，我們使用會議範本來設定下列設定：

- **允許出席**  -  者使用相機 **開** 啟但不針對會議強制執行，並強制 **關閉** 簡報。
- **允許出席**  -  者使用麥克風 **開** 啟但不針對會議強制執行，並強制 **關閉** 簡報。
- **管理出席者可以看到的內容** - 針對會議和 **簡報強制開** 啟。
- **會議聊天** - 針對會議強制只在 **會議中** 執行，並強制為 **[簡報] 為 [關閉** ]。

由於這些設定在會議和簡報之間有所不同，我們會為每個共用相同敏感度標籤的人員建立範本。

#### <a name="highly-sensitive-meetings-template"></a>高度機密的會議範本

建立高機密會議的會議範本

1. 在 Teams 系統管理中心中，展開 **[會議** ]，然後選取 **[會議範本]**。
1. 選取 **[新增]**
1. 輸入範本的名稱和描述。
1. 在 [ **套用敏感度標籤** ] 區段中，選擇您在上面建立的標籤。
1. 選 **取 [套用敏感度標籤**]，然後選取 [ **鎖定]**。
1. 將 **[會議聊天** ] 設定為 **[僅限會議]** ，然後選取設定，然後選取 **[鎖定]**。
1. 將 **[管理出席者看到的內容** ] 設定為 [ **開啟** ]，然後選取設定，然後選取 **[鎖定]**。
1. 如有需要，請變更任何其他設定。
1. 若要防止會議召集人變更設定，請選取設定，然後選取 **[鎖定]**。
1. 若要防止會議召集人看到設定，請選取設定，然後選取 **[隱藏]**。
1. 選取 [儲存 **]**。

#### <a name="highly-sensitive-presentations-template"></a>高度敏感性簡報範本

為高度敏感性簡報建立會議範本

1. 在 Teams 系統管理中心中，展開 **[會議** ]，然後選取 **[會議範本]**。
1. 選取 **[新增]**
1. 輸入範本的名稱和描述。
1. 在 [ **套用敏感度標籤** ] 區段中，選擇您在上面建立的標籤。
1. 選 **取 [套用敏感度標籤**]，然後選取 [ **鎖定]**。
1. 將 **[允許出席者麥克風** ] 設定為 [ **開啟]** ，然後選取設定，然後選取 **[鎖定]**。
1. 將 **[允許出席者使用相機** ] 設定為 [ **開啟** ]，然後選取設定，然後選取 **[鎖定]**。
1. 將 **[會議聊天** ] 設定為 **[關閉]** ，然後選取設定，然後選取 **[鎖定]**。
1. 將 **[管理出席者看到的內容** ] 設定為 [ **開啟** ]，然後選取設定，然後選取 **[鎖定]**。
1. 如有需要，請變更任何其他設定。
1. 若要防止會議召集人變更設定，請選取設定，然後選取 **[鎖定]**。
1. 若要防止會議召集人看到設定，請選取設定，然後選取 **[隱藏]**。
1. 選取 [儲存 **]**。

## <a name="related-topics"></a>相關主題

[設定具有三層保護層級的 Teams 會議](configure-meetings-three-tiers-protection.md)

[Microsoft Teams 中的自訂會議範本概觀](custom-meeting-templates-overview.md)

[搭配使用 Teams 會議範本、敏感度標籤和系統管理原則來進行敏感性會議](meeting-templates-sensitivity-labels-policies.md)

[使用敏感度標籤來保護行事曆專案、Teams 會議和聊天](/microsoft-365/compliance/sensitivity-labels-meetings)
