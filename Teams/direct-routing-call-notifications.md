---
title: 管理直接路由的通話通知
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 10/17/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: filippse
search.appverid: MET150
f1.keywords:
- NOCSH
description: 直接路由通話通知
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: 4aa8e6a6f75141f7858e2342b65fb59d09326c33
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2022
ms.locfileid: "67268428"
---
# <a name="manage-call-notifications"></a>管理來電通知

本文說明如何管理直接路由使用者的通話通知。 您可以將通話端點設定為 Teams 和協力廠商 Private Branch Exchange (PBX) 或會話框線控制器 (SBC) 。 舉例來說，如果您想要同時將電話傳送到使用者的行動裝置和電話機，這項設定就很實用。   

在下列圖表中，使用者 Irena 有兩個端點：

- Teams 端點
- 連線至協力廠商 SBC 的 SIP 手機

當電話送達時，SBC 會在直接路由和協力廠商 SBC 之間分隔通話。


![顯示分叉 Teams 端點的圖表。](media/direct-routing-call-notification-1.png)

如果協力廠商 SBC) 在 Fork 2 (接聽來電，Teams 會產生「未接來電」通知。  

您可以將 SBC 設定為在 Fork 1 上傳送取消，以避免出現「未接來電」通知，如下所示：

原因：SIP;cause=200;text「Call completed elsewhere」 

通話不會在 Teams 電話系統的通話詳細資料記錄中註冊為成功的通話。 通話會登錄為「嘗試」，並包含最終 SIP 代碼 「487」、最終 Microsoft 子代碼 「540200」，以及最終 SIP 代碼片語「在其他地方完成通話」。   (若要檢視通話詳細資料記錄，請移至 Teams 管理員 中心 ->**分析與報告**  ->  **使用方式報告**]，然後選取 **[PSTN 使用方式**]。) 


下圖說明 Fork 1 的 SIP 介面、說明通話流程，以及取消訊息中的預期原因。 

![圖表顯示分派的 Teams 端點。](media/direct-routing-call-notification-2.png)
