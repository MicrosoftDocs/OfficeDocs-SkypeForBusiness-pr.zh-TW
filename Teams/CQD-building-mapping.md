---
title: '在 CQD 中建立通話品質儀表板 (地圖) '
ms.author: serdars
author: SerdarSoysal
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
description: 瞭解如何建立建築物地圖，您可以在 CQD (中上傳租使用者和) 。
ms.openlocfilehash: 890e5e9b394cf8b600e635014c90ebb9053a1e07
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "46584032"
---
# <a name="create-a-building-map-for-call-quality-dashboard-cqd"></a><span data-ttu-id="bf0d3-103">在 CQD 中建立通話品質儀表板 (地圖) </span><span class="sxs-lookup"><span data-stu-id="bf0d3-103">Create a building map for Call Quality Dashboard (CQD)</span></span>

<span data-ttu-id="bf0d3-104">在線上Microsoft Teams或商務用 Skype部署中，所有用戶端都是外部的。</span><span class="sxs-lookup"><span data-stu-id="bf0d3-104">In a Microsoft Teams or Skype for Business Online deployment, all clients are external.</span></span> <span data-ttu-id="bf0d3-105">因此，根據預設，所有用戶端都會在通話品質儀表板 (CQD) 中報告為外部，無論用戶端是否已在內部公司網路上連接。</span><span class="sxs-lookup"><span data-stu-id="bf0d3-105">As a result, by default, all clients are reported as outside in Call Quality Dashboard (CQD), regardless of whether the client is connected on an internal corporate network.</span></span>

<span data-ttu-id="bf0d3-106">當您使用 CQD 時，您必須知道端點的位置，以及端點是否連接到您可以管理的網路或無法管理的網路，前提是只能改善您可以管理的網路。</span><span class="sxs-lookup"><span data-stu-id="bf0d3-106">When you work with CQD, you need to know the location of an endpoint and whether it was connected to a network you can manage or a network you can't manage, the assumption being that you can only improve networks you can manage.</span></span> <span data-ttu-id="bf0d3-107">將子網和建築物資訊上傳至 CQD，您可以啟用 CQD 來判斷端點是否已連接到內部 (受管理的) 網路，或已 (未管理的) 網路。</span><span class="sxs-lookup"><span data-stu-id="bf0d3-107">By uploading subnet and building information to CQD, you enable CQD to determine whether the endpoint was connected to an internal (managed) network or to an external (unmanaged) network.</span></span> <span data-ttu-id="bf0d3-108">這就是為什麼為貴組織建立建築物地圖並將其上傳到 [CQD](CQD-upload-tenant-building-data.md)非常重要的原因。</span><span class="sxs-lookup"><span data-stu-id="bf0d3-108">That's why it's important to create a building map for your organization and [upload it to CQD](CQD-upload-tenant-building-data.md).</span></span>

## <a name="building-mapping-tools"></a><span data-ttu-id="bf0d3-109">建立地圖工具</span><span class="sxs-lookup"><span data-stu-id="bf0d3-109">Building mapping tools</span></span>

<span data-ttu-id="bf0d3-110">有許多方法可以映射貴組織的子網。</span><span class="sxs-lookup"><span data-stu-id="bf0d3-110">There are many ways to map your organization's subnets.</span></span> <span data-ttu-id="bf0d3-111">如果您需要協助，您可以使用這篇部落格文章中所述的 CQDTools PowerShell [模組](https://aka.ms/cqdtools)。</span><span class="sxs-lookup"><span data-stu-id="bf0d3-111">If you need help, you can use the CQDTools PowerShell Module described in this [blog post](https://aka.ms/cqdtools).</span></span> <span data-ttu-id="bf0d3-112">這些工具是以 PowerShell 為基礎，並使用 Active Directory (AD) 網站與服務和 Microsoft DHCP 服務，協助預先填入您的建房檔案。</span><span class="sxs-lookup"><span data-stu-id="bf0d3-112">These tools are based on PowerShell and use Active Directory (AD) Sites and Services and Microsoft DHCP services to help pre-populate your building file.</span></span> <span data-ttu-id="bf0d3-113">這些工具可協助進行下列工作：</span><span class="sxs-lookup"><span data-stu-id="bf0d3-113">These tools will help with the following tasks:</span></span>

1. <span data-ttu-id="bf0d3-114">查詢 AD 網站和服務，然後根據所包含的資訊建立建房檔案。</span><span class="sxs-lookup"><span data-stu-id="bf0d3-114">Query AD Sites and Services, and create a building file based on the information contained within.</span></span>
1. <span data-ttu-id="bf0d3-115">查詢 Microsoft DHCP 伺服器或伺服器以提取子網資訊，並自動建立建築物檔案。</span><span class="sxs-lookup"><span data-stu-id="bf0d3-115">Query a Microsoft DHCP server or servers to pull subnet information and automatically create a building file.</span></span>
1. <span data-ttu-id="bf0d3-116">驗證現有的建築物檔案，檢查重複和重迭。</span><span class="sxs-lookup"><span data-stu-id="bf0d3-116">Validate an existing building file, checking for duplicates and overlaps.</span></span>
1. <span data-ttu-id="bf0d3-117">在 CQD 中尋找未映射的子網。</span><span class="sxs-lookup"><span data-stu-id="bf0d3-117">Find unmapped subnets in CQD.</span></span>

## <a name="related-topics"></a><span data-ttu-id="bf0d3-118">相關主題</span><span class="sxs-lookup"><span data-stu-id="bf0d3-118">Related topics</span></span>

[<span data-ttu-id="bf0d3-119">Upload CQD 中建立租使用者和建築物資料</span><span class="sxs-lookup"><span data-stu-id="bf0d3-119">Upload tenant and building data in CQD</span></span>](CQD-upload-tenant-building-data.md)