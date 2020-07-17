---
title: 為通話品質儀表板（CQD）建立地圖
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: 瞭解如何建立您可以用來在通話品質儀表板（CQD）中上傳租使用者和組建資料的組建地圖。
ms.openlocfilehash: 18e88c2de64d2d63589a3cd2ebddbc9643fe4522
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086043"
---
# <a name="create-a-building-map-for-call-quality-dashboard-cqd"></a><span data-ttu-id="6a136-103">為通話品質儀表板（CQD）建立地圖</span><span class="sxs-lookup"><span data-stu-id="6a136-103">Create a building map for Call Quality Dashboard (CQD)</span></span>

<span data-ttu-id="6a136-104">在 Microsoft 團隊或商務用 Skype Online 部署中，所有用戶端都是外部的。</span><span class="sxs-lookup"><span data-stu-id="6a136-104">In a Microsoft Teams or Skype for Business Online deployment, all clients are external.</span></span> <span data-ttu-id="6a136-105">因此，根據預設，所有用戶端都會在通話品質儀表板（CQD）中報告為外部，不論用戶端是否已連線至內部公司網路。</span><span class="sxs-lookup"><span data-stu-id="6a136-105">As a result, by default, all clients are reported as outside in Call Quality Dashboard (CQD), regardless of whether the client is connected on an internal corporate network.</span></span>

<span data-ttu-id="6a136-106">當您使用 CQD 時，您必須知道端點的位置，以及它是否已連線到您可以管理的網路，或是您無法管理的網路，假設您只能改善您可以管理的網路。</span><span class="sxs-lookup"><span data-stu-id="6a136-106">When you work with CQD, you need to know the location of an endpoint and whether it was connected to a network you can manage or a network you can't manage, the assumption being that you can only improve networks you can manage.</span></span> <span data-ttu-id="6a136-107">透過將子網和組建資訊上傳到 CQD，您可以讓 CQD 判斷端點是連線到內部（受管理的）網路或外部（未受管理的）網路。</span><span class="sxs-lookup"><span data-stu-id="6a136-107">By uploading subnet and building information to CQD, you enable CQD to determine whether the endpoint was connected to an internal (managed) network or to an external (unmanaged) network.</span></span> <span data-ttu-id="6a136-108">這就是為什麼為貴組織建立組建地圖並[將其上傳到 CQD](CQD-upload-tenant-building-data.md)很重要的原因。</span><span class="sxs-lookup"><span data-stu-id="6a136-108">That's why it's important to create a building map for your organization and [upload it to CQD](CQD-upload-tenant-building-data.md).</span></span>

## <a name="building-mapping-tools"></a><span data-ttu-id="6a136-109">建立地圖工具</span><span class="sxs-lookup"><span data-stu-id="6a136-109">Building mapping tools</span></span>

<span data-ttu-id="6a136-110">您可以透過多種方式來對應貴組織的子網。</span><span class="sxs-lookup"><span data-stu-id="6a136-110">There are many ways to map your organization's subnets.</span></span> <span data-ttu-id="6a136-111">如果您需要協助，您可以使用此[博客文章](https://aka.ms/cqdtools)中所述的 CQDTools PowerShell 模組。</span><span class="sxs-lookup"><span data-stu-id="6a136-111">If you need help, you can use the CQDTools PowerShell Module described in this [blog post](https://aka.ms/cqdtools).</span></span> <span data-ttu-id="6a136-112">這些工具是以 PowerShell 為基礎，並使用 Active Directory （AD）網站和服務與 Microsoft DHCP 服務協助預先填入您的組建檔案。</span><span class="sxs-lookup"><span data-stu-id="6a136-112">These tools are based on PowerShell and use Active Directory (AD) Sites and Services and Microsoft DHCP services to help pre-populate your building file.</span></span> <span data-ttu-id="6a136-113">這些工具將協助您執行下列任務：</span><span class="sxs-lookup"><span data-stu-id="6a136-113">These tools will help with the following tasks:</span></span>

1. <span data-ttu-id="6a136-114">查詢廣告網站和服務，並根據所含的資訊建立組建檔案。</span><span class="sxs-lookup"><span data-stu-id="6a136-114">Query AD Sites and Services, and create a building file based on the information contained within.</span></span>
1. <span data-ttu-id="6a136-115">查詢 Microsoft DHCP 伺服器或伺服器以抽取子網資訊並自動建立組建檔案。</span><span class="sxs-lookup"><span data-stu-id="6a136-115">Query a Microsoft DHCP server or servers to pull subnet information and automatically create a building file.</span></span>
1. <span data-ttu-id="6a136-116">驗證現有的建築物檔案、檢查重複專案和重疊。</span><span class="sxs-lookup"><span data-stu-id="6a136-116">Validate an existing building file, checking for duplicates and overlaps.</span></span>
1. <span data-ttu-id="6a136-117">在 CQD 中尋找未對應的子網。</span><span class="sxs-lookup"><span data-stu-id="6a136-117">Find unmapped subnets in CQD.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6a136-118">相關主題</span><span class="sxs-lookup"><span data-stu-id="6a136-118">Related topics</span></span>

[<span data-ttu-id="6a136-119">在 CQD 中上傳租使用者和組建資料</span><span class="sxs-lookup"><span data-stu-id="6a136-119">Upload tenant and building data in CQD</span></span>](CQD-upload-tenant-building-data.md)