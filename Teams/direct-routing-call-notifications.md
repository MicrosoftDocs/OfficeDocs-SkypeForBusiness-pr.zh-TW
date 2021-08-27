---
title: Teams：管理通話通知
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
ms.localizationpriority: medium
ms.openlocfilehash: 27e06a45cef49f2291fdf75a8375026b9a930953
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58617409"
---
# <a name="manage-call-notifications"></a>管理來電通知

本文將說明如何管理使用者的通話通知。 您可以將呼叫端點設定為 Teams 或協力廠商私人分支 Exchange (PBX) 或會話邊界控制器 (SBC) 。  例如，如果您想要同時將電話傳送至使用者的行動電話和電話機，這項設定就很有用。   

在下列圖表中，使用者 Irena 有兩個端點：

- Teams端點
- 已連接至協力廠商 SBC 的 SIP 電話

當來電到達時，SBC 會電話系統直接路由和協力廠商 SBC 之間的通話。


![顯示分叉端點Teams圖表](media/direct-routing-call-notification-1.png)

如果協力廠商 SBC (在 fork 2 上接受) ，Teams就會產生「未接來電」通知。  

您可以按照以下方式，將 SBC 在 Fork 1 上傳送 Cancel，以防止「未接來電」通知：

原因：SIP;cause=200;text"通話在其他地方完成」 

通話不會在系統電話的詳細Microsoft 電話記錄中註冊為成功的通話。 通話會以「嘗試」註冊為「嘗試」，包含 「487」、Final Microsoft 子代碼「540200」，以及「在其他地方完成通話」的最後 SIP 程式碼片語。   (若要查看通話詳細資料記錄，請前往 [Teams 系統管理入口網站、[分析與報告) 


下圖說明 Fork 1 的 SIP 梯級，說明通話流程，以及取消訊息中的預期原因。 

![圖表顯示分叉Teams端點](media/direct-routing-call-notification-2.png)
