---
title: 商務用 Skype Server 2015 中的 Mcus 表格
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
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: Mcus 表格是支援的表格。 每筆記錄儲存一筆會議服務的相關資訊。 這些可包含 IM 會議服務和電話語音會議服務 (，此服務會在前端伺服器上執行為處理常式) ，以及 Web 會議服務和 A/V 會議服務。
ms.openlocfilehash: fe43bfc747cd08febe00a68925ad520b6add5846
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821423"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a><span data-ttu-id="3a46b-105">商務用 Skype Server 2015 中的 Mcus 表格</span><span class="sxs-lookup"><span data-stu-id="3a46b-105">Mcus table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="3a46b-106">Mcus 表格是支援的表格。</span><span class="sxs-lookup"><span data-stu-id="3a46b-106">The Mcus table is a supporting table.</span></span> <span data-ttu-id="3a46b-107">每筆記錄儲存一筆會議服務的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="3a46b-107">Each record stores information about one conferencing service.</span></span> <span data-ttu-id="3a46b-108">這些可包含 IM 會議服務和電話語音會議服務 (，此服務會在前端伺服器上執行為處理常式) ，以及 Web 會議服務和 A/V 會議服務。</span><span class="sxs-lookup"><span data-stu-id="3a46b-108">These can include the IM Conferencing service and the Telephony Conferencing service (which run as processes on front-end servers), and the Web Conferencing service and A/V Conferencing service.</span></span> 
  
|<span data-ttu-id="3a46b-109">**欄**</span><span class="sxs-lookup"><span data-stu-id="3a46b-109">**Column**</span></span>|<span data-ttu-id="3a46b-110">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="3a46b-110">**Data Type**</span></span>|<span data-ttu-id="3a46b-111">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="3a46b-111">**Key/Index**</span></span>|<span data-ttu-id="3a46b-112">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="3a46b-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3a46b-113">**McuId**</span><span class="sxs-lookup"><span data-stu-id="3a46b-113">**McuId**</span></span> <br/> |<span data-ttu-id="3a46b-114">int</span><span class="sxs-lookup"><span data-stu-id="3a46b-114">int</span></span>  <br/> |<span data-ttu-id="3a46b-115">主要</span><span class="sxs-lookup"><span data-stu-id="3a46b-115">Primary</span></span>  <br/> |<span data-ttu-id="3a46b-116">用於識別此會議服務器的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="3a46b-116">Unique number identifying this conferencing server.</span></span>  <br/> |
|<span data-ttu-id="3a46b-117">**McuUri**</span><span class="sxs-lookup"><span data-stu-id="3a46b-117">**McuUri**</span></span> <br/> |<span data-ttu-id="3a46b-118">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="3a46b-118">nvarchar(450)</span></span>  <br/> | <br/> | <br/> |
|<span data-ttu-id="3a46b-119">**McuTypeId**</span><span class="sxs-lookup"><span data-stu-id="3a46b-119">**McuTypeId**</span></span> <br/> |<span data-ttu-id="3a46b-120">inyint</span><span class="sxs-lookup"><span data-stu-id="3a46b-120">inyint</span></span>  <br/> | <span data-ttu-id="3a46b-121">Foreign</span><span class="sxs-lookup"><span data-stu-id="3a46b-121">Foreign</span></span> <br/> |<span data-ttu-id="3a46b-122">會議服務器類型，例如會議： Im) 或會議：音訊-影片的聊天室 (。</span><span class="sxs-lookup"><span data-stu-id="3a46b-122">Conferencing server type, such as conf:chat (for IMs) or conf:audio-video.</span></span> <span data-ttu-id="3a46b-123">如需詳細資訊，請參閱 [UriTypes 表格](uritypes.md) 。</span><span class="sxs-lookup"><span data-stu-id="3a46b-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

