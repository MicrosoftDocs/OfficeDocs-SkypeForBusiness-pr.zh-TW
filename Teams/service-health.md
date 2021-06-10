---
title: 驗證服務健康Microsoft Teams
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
description: 最佳做法是確認 Teams 服務以及其他 Microsoft 365 或 Office 365 元件 ，例如 Exchange、SharePoint 和 商務用 OneDrive。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 53184bbdc25cc96e667cd8c0ddff9eae5bfdfe8c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51107509"
---
<a name="verify-service-health-for-microsoft-teams"></a><span data-ttu-id="17355-103">驗證服務健康Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="17355-103">Verify service health for Microsoft Teams</span></span>
===========================================

<span data-ttu-id="17355-104">系統管理中心Microsoft Teams顯示Microsoft 365健康狀態。</span><span class="sxs-lookup"><span data-stu-id="17355-104">Service health for Microsoft Teams is displayed on the Microsoft 365 admin center.</span></span> <span data-ttu-id="17355-105">在疑難排解問題之前，最佳做法是確認服務Teams正常。</span><span class="sxs-lookup"><span data-stu-id="17355-105">Before troubleshooting issues, it's a good practice to verify that the Teams service is healthy.</span></span> <span data-ttu-id="17355-106">請前往服務<a href=" https://admin.microsoft.com/adminportal/home?ref=servicehealth" target="_blank">Teams</a>主控台，以檢查服務健康狀態。</span><span class="sxs-lookup"><span data-stu-id="17355-106">Go to the <a href=" https://admin.microsoft.com/adminportal/home?ref=servicehealth" target="_blank">Teams Service Health</a> console to review the service health.</span></span>

<span data-ttu-id="17355-107">此外，請記住，Microsoft Teams是建在額外的 Microsoft 365 或 Office 365 服務上，因此在查看服務健康情況時，請記得同時檢查 Exchange、SharePoint 和 商務用 OneDrive 的狀態。</span><span class="sxs-lookup"><span data-stu-id="17355-107">Also, keep in mind that, Microsoft Teams is built on top of additional Microsoft 365 or Office 365 services, so when looking at Service Health, remember to also check the status of Exchange, SharePoint, and OneDrive for Business.</span></span> <span data-ttu-id="17355-108">這些其他服務的服務健康情況問題不會自動表示 Teams 受到影響 (例如 Exchange 中的通訊錄下載無法使用) ，但您應檢查受影響服務的建議，判斷對 Microsoft Teams 是否有影響。</span><span class="sxs-lookup"><span data-stu-id="17355-108">Service Health issues for these other services does not automatically mean that Teams is impacted (e.g. Address Book downloads in Exchange are unavailable), but that you should review the advisories for those affected services to determine if there is an impact to Microsoft Teams.</span></span>

![服務健康情況頁面的螢幕擷取畫面。](media/Verify_service_health_for_Microsoft_Teams_image1.png)

![顯示服務Microsoft Teams的螢幕擷取畫面。](media/Verify_service_health_for_Microsoft_Teams_image2.png)


## <a name="related-topics"></a><span data-ttu-id="17355-111">相關主題</span><span class="sxs-lookup"><span data-stu-id="17355-111">Related topics</span></span>

[<span data-ttu-id="17355-112">Teams 疑難排解</span><span class="sxs-lookup"><span data-stu-id="17355-112">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)