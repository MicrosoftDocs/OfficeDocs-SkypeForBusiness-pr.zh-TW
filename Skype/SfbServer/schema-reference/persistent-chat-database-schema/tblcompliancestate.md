---
title: tblComplianceState
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState 包含全池相容性狀態資訊。
ms.openlocfilehash: 1c5571d7150c3859978f8d217f0264f67ee993d5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192746"
---
# <a name="tblcompliancestate"></a><span data-ttu-id="c40ae-103">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="c40ae-103">tblComplianceState</span></span>
 
<span data-ttu-id="c40ae-104">tblComplianceState 包含全池相容性狀態資訊。</span><span class="sxs-lookup"><span data-stu-id="c40ae-104">tblComplianceState contains pool-wide compliance state information.</span></span>
  
<span data-ttu-id="c40ae-105">**分欄**</span><span class="sxs-lookup"><span data-stu-id="c40ae-105">**Columns**</span></span>

|<span data-ttu-id="c40ae-106">**左欄**</span><span class="sxs-lookup"><span data-stu-id="c40ae-106">**Column**</span></span>|<span data-ttu-id="c40ae-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="c40ae-107">**Type**</span></span>|<span data-ttu-id="c40ae-108">**說明**</span><span class="sxs-lookup"><span data-stu-id="c40ae-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c40ae-109">lastProcessedEntryID</span><span class="sxs-lookup"><span data-stu-id="c40ae-109">lastProcessedEntryID</span></span>  <br/> |<span data-ttu-id="c40ae-110">Bigint, not null</span><span class="sxs-lookup"><span data-stu-id="c40ae-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="c40ae-111">最新處理的相容性事件識別碼。</span><span class="sxs-lookup"><span data-stu-id="c40ae-111">ID of the latest processed compliance event.</span></span>  <br/> |
|<span data-ttu-id="c40ae-112">activeServerID</span><span class="sxs-lookup"><span data-stu-id="c40ae-112">activeServerID</span></span>  <br/> |<span data-ttu-id="c40ae-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="c40ae-113">int, not null</span></span>  <br/> |<span data-ttu-id="c40ae-114">在資料庫上保留獨佔鎖的規範伺服器識別碼, 或者如果沒有, 則為-1。</span><span class="sxs-lookup"><span data-stu-id="c40ae-114">ID of the Compliance server holding the exclusive lock on the database, or -1 if none.</span></span>  <br/> |
|<span data-ttu-id="c40ae-115">lockExpirationTime</span><span class="sxs-lookup"><span data-stu-id="c40ae-115">lockExpirationTime</span></span>  <br/> |<span data-ttu-id="c40ae-116">datetime2, not null</span><span class="sxs-lookup"><span data-stu-id="c40ae-116">datetime2, not null</span></span>  <br/> |<span data-ttu-id="c40ae-117">鎖定到期時間 (如果 activeServerID 不是-1)。</span><span class="sxs-lookup"><span data-stu-id="c40ae-117">Lock expiration time (if activeServerID is not -1).</span></span>  <br/> |
   

