---
title: 驗證 Microsoft Teams 的服務健康狀態
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
description: 最佳做法是確認 Teams 服務和其他 Microsoft 365 或 Office 365 元件 ，例如 Exchange、SharePoint 和商務用 OneDrive 是否正常。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 53184bbdc25cc96e667cd8c0ddff9eae5bfdfe8c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51107509"
---
<a name="verify-service-health-for-microsoft-teams"></a>驗證 Microsoft Teams 的服務健康狀態
===========================================

Microsoft Teams 的服務健康狀態會顯示在 Microsoft 365 系統管理中心。 在疑難排解問題之前，最佳做法是確認 Teams 服務是否正常。 請前往 <a href=" https://admin.microsoft.com/adminportal/home?ref=servicehealth" target="_blank">Teams 服務健康狀態</a> 主控台，以檢查服務健康狀態。

此外，請記住，Microsoft Teams 是建在其他 Microsoft 365 或 Office 365 服務上，因此查看服務健康情況時，請記得同時檢查 Exchange、SharePoint 和商務用 OneDrive 的狀態。 這些其他服務的服務健康情況問題不會自動表示 Teams 受到影響 (例如 Exchange 中的通訊錄下載無法使用) ，但您應檢查這些受影響服務的意見建議，以判斷是否會影響 Microsoft Teams。

![服務健康情況頁面的螢幕擷取畫面。](media/Verify_service_health_for_Microsoft_Teams_image1.png)

![螢幕擷取畫面顯示 Microsoft Teams 服務正常。](media/Verify_service_health_for_Microsoft_Teams_image2.png)


## <a name="related-topics"></a>相關主題

[Teams 疑難排解](/MicrosoftTeams/troubleshoot/teams)