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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState 包含全池相容性狀態資訊。
ms.openlocfilehash: 6f3a7b1b7744260d0630a5328021b1752137a797
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814631"
---
# <a name="tblcompliancestate"></a><span data-ttu-id="f1aac-103">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="f1aac-103">tblComplianceState</span></span>
 
<span data-ttu-id="f1aac-104">tblComplianceState 包含全池相容性狀態資訊。</span><span class="sxs-lookup"><span data-stu-id="f1aac-104">tblComplianceState contains pool-wide compliance state information.</span></span>
  
<span data-ttu-id="f1aac-105">**分欄**</span><span class="sxs-lookup"><span data-stu-id="f1aac-105">**Columns**</span></span>

|<span data-ttu-id="f1aac-106">**左欄**</span><span class="sxs-lookup"><span data-stu-id="f1aac-106">**Column**</span></span>|<span data-ttu-id="f1aac-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="f1aac-107">**Type**</span></span>|<span data-ttu-id="f1aac-108">**說明**</span><span class="sxs-lookup"><span data-stu-id="f1aac-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f1aac-109">lastProcessedEntryID</span><span class="sxs-lookup"><span data-stu-id="f1aac-109">lastProcessedEntryID</span></span>  <br/> |<span data-ttu-id="f1aac-110">Bigint，not null</span><span class="sxs-lookup"><span data-stu-id="f1aac-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="f1aac-111">最新處理的相容性事件識別碼。</span><span class="sxs-lookup"><span data-stu-id="f1aac-111">ID of the latest processed compliance event.</span></span>  <br/> |
|<span data-ttu-id="f1aac-112">activeServerID</span><span class="sxs-lookup"><span data-stu-id="f1aac-112">activeServerID</span></span>  <br/> |<span data-ttu-id="f1aac-113">int，not null</span><span class="sxs-lookup"><span data-stu-id="f1aac-113">int, not null</span></span>  <br/> |<span data-ttu-id="f1aac-114">在資料庫上保留獨佔鎖的規範伺服器識別碼，或者如果沒有，則為-1。</span><span class="sxs-lookup"><span data-stu-id="f1aac-114">ID of the Compliance server holding the exclusive lock on the database, or -1 if none.</span></span>  <br/> |
|<span data-ttu-id="f1aac-115">lockExpirationTime</span><span class="sxs-lookup"><span data-stu-id="f1aac-115">lockExpirationTime</span></span>  <br/> |<span data-ttu-id="f1aac-116">datetime2，not null</span><span class="sxs-lookup"><span data-stu-id="f1aac-116">datetime2, not null</span></span>  <br/> |<span data-ttu-id="f1aac-117">鎖定到期時間（如果 activeServerID 不是-1）。</span><span class="sxs-lookup"><span data-stu-id="f1aac-117">Lock expiration time (if activeServerID is not -1).</span></span>  <br/> |
   

