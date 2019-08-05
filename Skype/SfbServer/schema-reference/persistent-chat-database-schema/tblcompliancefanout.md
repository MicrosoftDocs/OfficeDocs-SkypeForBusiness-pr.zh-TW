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
localization_priority: Normal
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: tblComplianceFanout 包含已處理合規性事件的所有伺服器。
ms.openlocfilehash: 1d2dfc99619e0669a08db33dbacc75930053f0dc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192748"
---
# <a name="tblcompliancefanout"></a><span data-ttu-id="b3148-103">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="b3148-103">tblComplianceFanout</span></span>
 
<span data-ttu-id="b3148-104">tblComplianceFanout 包含已處理合規性事件的所有伺服器。</span><span class="sxs-lookup"><span data-stu-id="b3148-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>
  
<span data-ttu-id="b3148-105">**分欄**</span><span class="sxs-lookup"><span data-stu-id="b3148-105">**Columns**</span></span>

|<span data-ttu-id="b3148-106">**左欄**</span><span class="sxs-lookup"><span data-stu-id="b3148-106">**Column**</span></span>|<span data-ttu-id="b3148-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="b3148-107">**Type**</span></span>|<span data-ttu-id="b3148-108">**說明**</span><span class="sxs-lookup"><span data-stu-id="b3148-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b3148-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="b3148-109">fanoutEventID</span></span>  <br/> |<span data-ttu-id="b3148-110">int</span><span class="sxs-lookup"><span data-stu-id="b3148-110">int</span></span>  <br/> |<span data-ttu-id="b3148-111">事件 ID。</span><span class="sxs-lookup"><span data-stu-id="b3148-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="b3148-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="b3148-112">fanoutServerID</span></span>  <br/> |<span data-ttu-id="b3148-113">int</span><span class="sxs-lookup"><span data-stu-id="b3148-113">int</span></span>  <br/> |<span data-ttu-id="b3148-114">伺服器身分識別 (對應至 tblServerIdentity serverID 表)。</span><span class="sxs-lookup"><span data-stu-id="b3148-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span>  <br/> |
   
<span data-ttu-id="b3148-115">**快速鍵**</span><span class="sxs-lookup"><span data-stu-id="b3148-115">**Key**</span></span>

|<span data-ttu-id="b3148-116">**左欄**</span><span class="sxs-lookup"><span data-stu-id="b3148-116">**Column**</span></span>|<span data-ttu-id="b3148-117">**說明**</span><span class="sxs-lookup"><span data-stu-id="b3148-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b3148-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="b3148-118">fanoutEventID</span></span>  <br/> |<span data-ttu-id="b3148-119">在 tblComplianceData cmplEventID 資料表中使用 [查閱] 的外鍵。</span><span class="sxs-lookup"><span data-stu-id="b3148-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span>  <br/> |
   

