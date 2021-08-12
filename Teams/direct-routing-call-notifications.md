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
f1.keywords:
- NOCSH
description: 直接路由通話通知
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 0dea709f77cb971f8027bb848087f2da820f8007277abb227d2130da3e6a9058
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54284194"
---
# <a name="manage-call-notifications"></a>管理來電通知

本文將說明如何管理使用者的通話通知。 您可以將呼叫端點設定為協力廠商Teams或協力廠商私人分支 Exchange (PBX) 或會話邊界控制器 (SBC) 。  例如，如果您想要同時將電話傳送至使用者的行動電話和電話機，這項功能就很有用。   

在下列圖表中，使用者 Irena 有兩個端點：

- Teams端點
- 已連接至協力廠商 SBC 的 SIP 電話

當來電到達時，SBC 會電話系統直接路由和協力廠商 SBC 之間的通話。


![顯示分叉端點Teams圖表](media/direct-routing-call-notification-1.png)

如果協力廠商 SBC (在 fork 2 上接受) ，Teams就會產生「未接來電」通知。  

您可以按照以下方式，將 SBC 在 Fork 1 上傳送 Cancel，以防止「未接來電」通知：

原因：SIP;cause=200;text"通話在其他地方完成」 

請注意，系統不會將通話詳細Microsoft 電話記錄中註冊為成功的通話。 通話會以 「嘗試」註冊為「嘗試」，包含 「487」、「540200」的最終 Microsoft 子代碼，以及「在其他地方完成通話」的最後 SIP 程式碼片語。   (若要查看通話詳細資料記錄，請前往 [Teams 系統管理入口網站、分析與報告、使用方式報告，然後選取 [PSTN 使用方式) 


下圖說明 Fork 1 的 SIP 梯級，說明通話流程，以及取消訊息中的預期原因。 

![顯示分叉端點Teams圖表](media/direct-routing-call-notification-2.png)
