---
title: 使用通話分析來疑難排解不良通話品質
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.date: 03/08/2019
ms.topic: article
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.directrouting.callanalytics
- ms.teamsadmincenter.users.activity.audioqualitycolumn
- Reporting
description: 使用裝置、網路和連線的呼叫分析詳細資料，來針對 Microsoft 團隊及商務用 Skype 通話和會議的使用者問題進行疑難排解。
ms.openlocfilehash: 05af82a942d54e0f97f2be2b176091f19186cbf4
ms.sourcegitcommit: 48f64fa38509cf7141b944cd3da60409ec51860b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2020
ms.locfileid: "43749560"
---
# <a name="use-call-analytics-to-troubleshoot-poor-call-quality"></a>使用通話分析來疑難排解不良通話品質

[通話分析] 可協助您排查 Microsoft 團隊和商務用 Skype 的通話或連線問題。 [通話分析] 會顯示適用于 Office 365 帳戶中每位使用者之通話與會議的裝置、網路及連線能力的詳細資訊。 如果已將組建、網站和租使用者資訊新增至呼叫分析，也會針對每個通話和會話顯示該資訊。 透過 [呼叫分析] 提供的資訊可協助您瞭解使用者為何通話或會議感覺不佳的原因。 
  
## <a name="call-analytics-permissions"></a>呼叫分析許可權

就像管理員一樣，您就能完全存取通話分析的所有功能。 此外，您也可以將 Azure Active Directory 角色指派給支援人員。 將團隊通訊支援專家角色指派給應該擁有有限的通話分析視圖的使用者。 指派團隊通訊支援工程師角色給需要存取呼叫分析完整功能的使用者。 兩個許可權等級都無法存取 Microsoft 團隊系統管理中心的其他部分。

通訊支援專家處理基本的通話品質問題。 他們不會調查會議的問題。 相反地，他們會收集相關資訊，然後升級至通訊支援工程師。 通訊支援工程師請參閱與通訊支援專家隱藏的詳細通話記錄中的資訊。 下表提供通訊支援專家與通訊支援工程師在使用呼叫分析時所提供資訊的概覽。

指派給您的許可權等級決定了在通話分析中您有權存取哪些類型的資訊：
  
- **團隊服務管理員或團隊溝通系統管理員**：您可以存取通話分析及 Microsoft 團隊管理中心中的所有資訊。
    
- **團隊溝通支援專家**：您會在 [呼叫分析] 中看到一組有限的資料。 您可以對通話進行疑難排解，但您會將會議問題移交給小組通訊支援工程師。 您無法存取其他 Microsoft 團隊系統管理中心。
    
- **團隊溝通支援工程師**：您可以在通話分析中查看所有可用的資料，並協助疑難排解通話與會議的問題。 您無法存取其他 Microsoft 團隊系統管理中心。
    
> [!NOTE]
> 通訊支援專家角色相當於第1層支援，且溝通支援工程師角色相當於第2層支援。

如需有關團隊管理員角色的詳細資訊，請參閱[使用 Microsoft 團隊管理員角色管理團隊](using-admin-roles.md)。 如需團隊溝通支援專家與團隊溝通支援工程師角色的詳細比較，請參閱[設定呼叫分析](set-up-call-analytics.md#set-call-analytics-permissions) 
  
如果您需要許可權的協助，請參閱您的小組和商務用 Skype 系統管理員。
  
## <a name="troubleshoot-call-quality-problems-using-call-analytics"></a>使用通話分析進行通話品質問題的疑難排解

1. 使用您的小組通訊支援或團隊管理員認證登入。

2. 在您的網頁瀏覽器*https://admin.teams.microsoft.com*中，移至。
    
3. 在**儀表板**上的 [**使用者搜尋**] 中，開始輸入您要排除其來電之使用者的名稱或 sip 位址，或選取 [**查看使用者**] 來查看使用者清單。
    
    ![[通話分析] 使用者搜尋方塊的螢幕擷取畫面](media/use-call-analytics-to-troubleshoot-image-1.png)
  
4. 從清單中選取使用者。

5. 選取 [**通話記錄**]，然後選取您想要疑難排解的通話或會議。  最多可傳回500筆記錄。
    
    ![使用者 [通話記錄] 頁面的螢幕擷取畫面。](media/use-call-analytics-to-troubleshoot-image-2.png)
  
6. 選取 [**高級**] 索引標籤，然後尋找黃色和紅色專案，指出通話品質或連線問題不佳。
    
    在每個通話或會議的 [會話詳細資料] 中，次要問題會以黃色顯示。 （例如，在下列螢幕擷取畫面中，對於平均抖動、最大抖動及平均資料包遺失率而言，這些值都是黃色。）如果有黃色，則它不在正常範圍之內，可能會造成問題，但不太可能是問題的主要原因。 如果有紅色，這是一個很重要的問題，這可能是這個會話的通話品質不佳的主要原因。 
    
    ![使用者通話記錄的 [高級] 索引標籤的螢幕擷取畫面 ](media/use-call-analytics-to-troubleshoot-image-3.png)
  
在少數情況下，音訊會話的體驗資料品質不會收到。 這通常是由呼叫斷開並與用戶端端接所造成。 發生這種情況時，**無法使用**[會議評等]。
  
對於有經驗品質（QoE）資料的音訊會話，下表說明將會話限制為**不良**的主要問題。
  
|**問題**|**圖**|**描述**|
|:-----|:-----|:-----|
|撥號設定  <br/> |工作階段  <br/> |錯誤碼 Ms-診斷程式20-29 指出通話設定失敗。 使用者無法加入通話或會議。  <br/> |
|音訊網路分類不佳通話  <br/> |工作階段  <br/> |遇到網路品質問題（例如資料包遺失、抖動、NMOS 下降、RTT 或隱藏比率）。 如需有關用來將不佳通話分類之條件的詳細資訊，請參閱這篇[Microsoft 博客文章](https://go.microsoft.com/fwlink/p/?linkid=852133)。  <br/> |
|裝置無法運作  <br/> |裝置  <br/> | 裝置無法正常運作。 裝置的運作比例如下： <br/>  DeviceRenderNotFunctioningEventRatio >= 0.005 <br/>  DeviceCaptureNotFunctioningEventRatio >= 0.005 <br/> |
   
## <a name="related-topics"></a>相關主題
[設定通話分析](set-up-call-analytics.md)

[通話分析和通話品質儀表板](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 
