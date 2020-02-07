---
title: 驗證 Microsoft 團隊的服務健康情況
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
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
description: 最佳做法是確認團隊服務是否健康，以及其他 Office 365 元件（例如 Exchange、SharePoint 和商務用 OneDrive）。
appliesto:
- Microsoft Teams
ms.openlocfilehash: b61de9768de69830328f4ea789db1b8af7e7a24a
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41835733"
---
<a name="verify-service-health-for-microsoft-teams"></a><span data-ttu-id="efb98-103">驗證 Microsoft 團隊的服務健康情況</span><span class="sxs-lookup"><span data-stu-id="efb98-103">Verify service health for Microsoft Teams</span></span>
===========================================

<span data-ttu-id="efb98-104">Microsoft 團隊的服務健康情況會顯示在 Office 365 管理入口網站的主版頁面上。</span><span class="sxs-lookup"><span data-stu-id="efb98-104">Service health for Microsoft Teams is displayed on the Office 365 Admin portal main page.</span></span> <span data-ttu-id="efb98-105">在疑難排解問題之前，最好先確認團隊服務是否正常。</span><span class="sxs-lookup"><span data-stu-id="efb98-105">Before troubleshooting issues, it's a good practice to verify that the Teams service is healthy.</span></span>

<span data-ttu-id="efb98-106">此外，請記住，Microsoft 團隊是以其他 Office 365 服務為基礎，因此，當您查看服務健康情況時，請記得還要檢查 Exchange、SharePoint 和商務用 OneDrive 的狀態。</span><span class="sxs-lookup"><span data-stu-id="efb98-106">Also, keep in mind that, Microsoft Teams is built on top of additional Office 365 services, so when looking at Service Health, remember to also check the status of Exchange, SharePoint, and OneDrive for Business.</span></span> <span data-ttu-id="efb98-107">這些其他服務的服務健康情況問題不會自動表示小組受到影響（例如，Exchange 中的通訊錄下載無法使用），但是您應該查看該建議，以判斷這些受影響的服務是否有任何影響。Microsoft 團隊。</span><span class="sxs-lookup"><span data-stu-id="efb98-107">Service Health issues for these other services does not automatically mean that Teams is impacted (e.g. Address Book downloads in Exchange are unavailable), but that you should review the advisories for those affected services to determine if there is an impact to Microsoft Teams.</span></span>

![[服務健康情況] 頁面的螢幕擷取畫面。](media/Verify_service_health_for_Microsoft_Teams_image1.png)

![顯示 [Microsoft 團隊服務] 正常運行的螢幕擷取畫面。](media/Verify_service_health_for_Microsoft_Teams_image2.png)
