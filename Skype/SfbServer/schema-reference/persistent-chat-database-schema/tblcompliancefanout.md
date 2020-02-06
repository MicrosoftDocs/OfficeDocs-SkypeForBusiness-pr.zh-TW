---
title: tblComplianceFanout
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: tblComplianceFanout 包含已處理合規性事件的所有伺服器。
ms.openlocfilehash: cdf455563ccfc971963144b9d4e848d5678cac80
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814651"
---
# <a name="tblcompliancefanout"></a><span data-ttu-id="be33e-103">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="be33e-103">tblComplianceFanout</span></span>
 
<span data-ttu-id="be33e-104">tblComplianceFanout 包含已處理合規性事件的所有伺服器。</span><span class="sxs-lookup"><span data-stu-id="be33e-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>
  
<span data-ttu-id="be33e-105">**分欄**</span><span class="sxs-lookup"><span data-stu-id="be33e-105">**Columns**</span></span>

|<span data-ttu-id="be33e-106">**左欄**</span><span class="sxs-lookup"><span data-stu-id="be33e-106">**Column**</span></span>|<span data-ttu-id="be33e-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="be33e-107">**Type**</span></span>|<span data-ttu-id="be33e-108">**說明**</span><span class="sxs-lookup"><span data-stu-id="be33e-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="be33e-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="be33e-109">fanoutEventID</span></span>  <br/> |<span data-ttu-id="be33e-110">int</span><span class="sxs-lookup"><span data-stu-id="be33e-110">int</span></span>  <br/> |<span data-ttu-id="be33e-111">事件 ID。</span><span class="sxs-lookup"><span data-stu-id="be33e-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="be33e-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="be33e-112">fanoutServerID</span></span>  <br/> |<span data-ttu-id="be33e-113">int</span><span class="sxs-lookup"><span data-stu-id="be33e-113">int</span></span>  <br/> |<span data-ttu-id="be33e-114">伺服器身分識別（對應至 tblServerIdentity serverID 表）。</span><span class="sxs-lookup"><span data-stu-id="be33e-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span>  <br/> |
   
<span data-ttu-id="be33e-115">**機碼**</span><span class="sxs-lookup"><span data-stu-id="be33e-115">**Key**</span></span>

|<span data-ttu-id="be33e-116">**左欄**</span><span class="sxs-lookup"><span data-stu-id="be33e-116">**Column**</span></span>|<span data-ttu-id="be33e-117">**說明**</span><span class="sxs-lookup"><span data-stu-id="be33e-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="be33e-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="be33e-118">fanoutEventID</span></span>  <br/> |<span data-ttu-id="be33e-119">在 tblComplianceData cmplEventID 資料表中使用 [查閱] 的外鍵。</span><span class="sxs-lookup"><span data-stu-id="be33e-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span>  <br/> |
   

