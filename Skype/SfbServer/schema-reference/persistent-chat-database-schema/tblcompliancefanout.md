---
title: tblComplianceFanout
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: tblComplianceFanout 包含處理符合性事件的所有伺服器。
ms.openlocfilehash: 75e232cd464a2199b490e555c0fab79ded119c94
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809793"
---
# <a name="tblcompliancefanout"></a><span data-ttu-id="e7d1f-103">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="e7d1f-103">tblComplianceFanout</span></span>
 
<span data-ttu-id="e7d1f-104">tblComplianceFanout 包含處理符合性事件的所有伺服器。</span><span class="sxs-lookup"><span data-stu-id="e7d1f-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>
  
<span data-ttu-id="e7d1f-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="e7d1f-105">**Columns**</span></span>

|<span data-ttu-id="e7d1f-106">**欄**</span><span class="sxs-lookup"><span data-stu-id="e7d1f-106">**Column**</span></span>|<span data-ttu-id="e7d1f-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="e7d1f-107">**Type**</span></span>|<span data-ttu-id="e7d1f-108">**描述**</span><span class="sxs-lookup"><span data-stu-id="e7d1f-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e7d1f-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="e7d1f-109">fanoutEventID</span></span>  <br/> |<span data-ttu-id="e7d1f-110">int</span><span class="sxs-lookup"><span data-stu-id="e7d1f-110">int</span></span>  <br/> |<span data-ttu-id="e7d1f-111">事件識別碼。</span><span class="sxs-lookup"><span data-stu-id="e7d1f-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="e7d1f-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="e7d1f-112">fanoutServerID</span></span>  <br/> |<span data-ttu-id="e7d1f-113">int</span><span class="sxs-lookup"><span data-stu-id="e7d1f-113">int</span></span>  <br/> |<span data-ttu-id="e7d1f-114">與 tblServerIdentity.serverID table) 相對應的伺服器身分識別 (。</span><span class="sxs-lookup"><span data-stu-id="e7d1f-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span>  <br/> |
   
<span data-ttu-id="e7d1f-115">**Key**</span><span class="sxs-lookup"><span data-stu-id="e7d1f-115">**Key**</span></span>

|<span data-ttu-id="e7d1f-116">**欄**</span><span class="sxs-lookup"><span data-stu-id="e7d1f-116">**Column**</span></span>|<span data-ttu-id="e7d1f-117">**描述**</span><span class="sxs-lookup"><span data-stu-id="e7d1f-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e7d1f-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="e7d1f-118">fanoutEventID</span></span>  <br/> |<span data-ttu-id="e7d1f-119">在 tblComplianceData.cmplEventID 表格中查閱的外鍵。</span><span class="sxs-lookup"><span data-stu-id="e7d1f-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span>  <br/> |
   

