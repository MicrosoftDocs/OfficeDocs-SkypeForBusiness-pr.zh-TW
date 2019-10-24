---
title: 使用者封鎖的報告
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: 0ac844b2-1b08-4e5a-addf-03cde7af7a40
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: '此報告以及其他商務用 Skype 報告，提供活動的詳細資料，包括整個組織的 PSTN 使用量。 '
ms.openlocfilehash: 95269dc08806ab09a44f47153748d45a63fedbc2
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/18/2019
ms.locfileid: "37643011"
---
# <a name="users-blocked-report"></a>使用者封鎖的報告

新的商務用 Skype**報告**儀表板會顯示您組織中的商務用 skype 產品的活動概覽。 它可讓您深入探索個別的產品層級報表，讓您更精確地瞭解每個產品內的活動。 例如，您可以使用商務用**Skype 使用者封鎖**報表來查看貴組織中已封鎖進行 PSTN 通話的使用者。 此報告以及其他商務用 Skype 報告，提供活動的詳細資料，包括整個組織的 PSTN 使用量。
  
 查看[報表總覽](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)以取得更多可用報表。
  
> [!NOTE]
> 當您以系統管理員身分登入 Microsoft 365 系統管理中心時，您可以看到所有商務用 Skype 報告。 
  
## <a name="how-to-get-to-the-skype-for-business-users-blocked-report"></a>如何取得商務用 Skype 使用者封鎖的報告

![](../images/sfb-logo-30x30.png) **使用商務用 skype 系統管理中心**顯示商務用 skype 標誌的圖示

- 移至系統管理中心 > 系統**管理中心** > **商務用 Skype 系統管理中心** > **報告** > 已**封鎖的使用者**。
    
## <a name="interpret-the-skype-for-business-users-blocked-report"></a>解讀商務用 Skype 使用者封鎖的報告

您可以查看每個顯示的欄，以取得封鎖的使用者。
  
這就是報表看起來的樣子。 
  
![封鎖的使用者報告](../images/df50a413-7a51-4340-a59b-3f83de941762.png)

下表顯示所有封鎖的使用者進行通話的細目分類。 這會顯示指派給電話系統或音訊會議的所有使用者。 您可以在資料表中新增/移除資料行。
***
![數位1](../images/sfbcallout1.png)
*   [**使用者識別碼**] 是使用者的登入。
*   [**電話號碼**] 是指派給使用者的號碼。 
*   **封鎖動作時間**是指封鎖使用者撥打電話的時間（UTC）。
*   **封鎖動作**是封鎖使用者所採取的動作類型。
*   **封鎖動作原因**是封鎖使用者進行呼叫的原因。
***
![數位2](../images/sfbcallout2.png)<br/>
按一下以將欄拖曳至依據特定欄進行分組，如果您想要建立一個將一或多個欄中的所有資料組成群組的視圖 **，請在這裡拖曳欄標題**。
***
![數位3](../images/sfbcallout3.png)<br/>
您也可以按一下或敲擊 [**匯出至 excel** ] 按鈕，將報告資料匯出至 Excel .csv 檔案。

這會匯出所有使用者的資料，並可讓您進行簡單的排序與篩選，以進行進一步分析。 如果您的使用者少於2000個，您可以在報表本身的資料表中排序和篩選。 如果您有超過2000的使用者，若要篩選和排序，您必須匯出資料。
***

## <a name="want-to-see-other-skype-for-business-reports"></a>想要查看其他商務用 Skype 報表嗎？

- [商務用 Skype 活動報告](activity-report.md)您可以查看使用者使用對等、組織的方式，以及參與會議會話的數量。
    
- [商務用 Skype 裝置使用方式報告](device-usage-report.md)您可以查看裝置，包括已安裝商務用 Skype 應用程式的 Windows 作業系統和行動裝置，以及用於 IM 和會議的行動裝置。
    
- [商務用 Skype 會議召集人活動報告](conference-organizer-activity-report.md)您可以查看您的使用者使用 IM、音訊/視頻、應用程式共用、Web、撥入/取出-協力廠商以及撥入/登出-Microsoft 來組織會議的數量。
    
- [商務用 Skype 會議參與者活動報告](conference-participant-activity-report.md)您可以查看有多少 IM、音訊/視頻、應用程式共用、網頁和撥入/撥出會議會議都在參與。
    
- [商務用 Skype 對等活動報告](peer-to-peer-activity-report.md)您可以查看您的使用者使用 IM、音訊/視頻、應用程式共用和傳送檔案的數量。
    
- [商務用 SKYPE PSTN 使用方式報告](pstn-usage-report.md)您可以在輸入/撥出通話中看到所花費的分鐘數，以及這些通話的成本。

- [商務用 SKYPE PSTN 分鐘池報告](pstn-minute-pools-report.md)您可以查看貴組織內的當月所消耗的分鐘數。

- [商務用 Skype 會話詳細資料包表](session-details-report.md)您可以查看個別使用者的通話體驗的詳細資料。
   
## <a name="related-topics"></a>相關主題
[系統管理中心的活動報告](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
 