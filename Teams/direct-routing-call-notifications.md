---
title: 電話系統直接路由
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 10/17/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: nmurav
search.appverid: MET150
description: 直接路由呼叫通知
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: a031af6a7bdfedfebd6d666b717d03259d92f56c
ms.sourcegitcommit: 1aa98e3865d5a0f7be5e1cba497dea4ac7b9c607
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2019
ms.locfileid: "38074605"
---
# <a name="manage-call-notifications"></a>管理來電通知

本文說明如何管理使用者的呼叫通知。 您可以將呼叫端點設定為兩個小組，以及協力廠商的專用分支 Exchange （PBX）或會話邊界控制器（SBC）。  例如，如果您想要同時將呼叫傳送給使用者的行動裝置和手機，這會很有用。   

在下圖中，使用者 Irena 有兩個端點：

- 團隊端點
- 連接至協力廠商 SBC 的 SIP 電話

當來電到達時，SBC 會將電話系統 Direct 路由和協力廠商 SBC 之間的呼叫派生。


![顯示分叉團隊端點的圖表](media/direct-routing-call-notification-1.png)

如果在分叉2（由協力廠商 SBC）接受呼叫，小組會產生「未接來電」通知。  

您可以將 SBC 設定為在分叉1上傳送取消，以避免「未接來電」通知，如下所示：

原因： SIP;原因 = 200; 文字「通話完成于別處」 

請注意，通話不會在 Microsoft Phone 系統的通話詳細資料記錄中登入，因為這是成功的呼叫。 呼叫將會註冊為「嘗試」，其最終 SIP 程式碼為「487」、最終的 Microsoft 子代碼 "540200"，以及最後一個 SIP 程式碼片語「在別處完成通話」。   （若要查看通話詳細資料記錄，請移至 [團隊管理員] 入口網站、[分析與報告]、[使用方式報告]，然後選取 PSTN 使用量）。


下圖說明分叉1的 SIP 階梯，說明通話流程，以及取消訊息中的預期原因。 

![顯示分叉團隊端點的圖表](media/direct-routing-call-notification-2.png)
