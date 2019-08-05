---
title: 深入瞭解通話行識別碼與呼叫方名稱
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: 瞭解為何您需要新增在您使用 [新的當地號碼埠順序] 嚮導時可以變更帳戶的授權人員。
ms.openlocfilehash: e77176b978cb33df2bc4efebae11fb218c3932a5
ms.sourcegitcommit: 4bb900228cc55e0cbbce8c5b74b7de8df5a2288f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/23/2019
ms.locfileid: "36183558"
---
# <a name="more-about-calling-line-id-and-calling-party-name"></a><span data-ttu-id="b345b-103">深入瞭解通話行識別碼與呼叫方名稱</span><span class="sxs-lookup"><span data-stu-id="b345b-103">More about Calling Line ID and Calling Party Name</span></span>

<span data-ttu-id="b345b-104">CallerID (如通常所說的話), 實際上是由兩個面向使用者的可識別區塊所組成:</span><span class="sxs-lookup"><span data-stu-id="b345b-104">CallerID, as it is typically referred to, actually consists of two user-facing identifiable pieces of information:</span></span>
    - <span data-ttu-id="b345b-105">電話號碼 (通常稱為 CLID 或呼叫行識別碼)</span><span class="sxs-lookup"><span data-stu-id="b345b-105">A phone number (typically referred to as CLID or calling line ID)</span></span> 
    - <span data-ttu-id="b345b-106">呼叫參與方名稱 (通常稱為 CNAM), 最多可長達15個字元。</span><span class="sxs-lookup"><span data-stu-id="b345b-106">Calling party name (typically referred to as CNAM) which can be up to 15 characters in length.</span></span> 

<span data-ttu-id="b345b-107">通話時, CLID (電話號碼) 會傳送到目的地的載波 (也稱為 [終止載波])。</span><span class="sxs-lookup"><span data-stu-id="b345b-107">When a call is made, the CLID (phone number) is routed to the destination's carrier (also known as the terminating carrier).</span></span> <span data-ttu-id="b345b-108">通話的 CNAM 資訊可以或不與通話路由, 因為這取決於國家/地區如何實現 CNAM (如果有的話)。</span><span class="sxs-lookup"><span data-stu-id="b345b-108">The CNAM info for the call may or may not be routed with the call as this depends on how the country has implemented CNAM (if at all).</span></span> <span data-ttu-id="b345b-109">CNAM 傳送與通話的可靠性, 會根據將呼叫作為中間和/或終止載波來處理通話的國家和運營商而有所不同。</span><span class="sxs-lookup"><span data-stu-id="b345b-109">The reliability of CNAM delivery with the call varies depending on the country and carriers which handle the call either as an intermediary and/or a terminating carrier.</span></span> 

<span data-ttu-id="b345b-110">CLID & CNAM 傳輸是終止載波的責任, 因為端接運營商必須支援 CLID & CNAM 功能, 以及提供這兩個值的最新記錄。</span><span class="sxs-lookup"><span data-stu-id="b345b-110">CLID & CNAM transmission is the responsibility of the terminating carrier insofar as the terminating carrier must support CLID & CNAM functionality as well as provide up to date records for both values.</span></span> <span data-ttu-id="b345b-111">Microsoft 可靠地在起源撥打電話時提供 CLID 值, 但這些值在經過中間載波或終止載波後可能不會保持不變。</span><span class="sxs-lookup"><span data-stu-id="b345b-111">Microsoft reliably provides CLID values when originating calls, but those values may not be kept intact once they pass through an intermediary carrier or the terminating carrier.</span></span> <span data-ttu-id="b345b-112">遺憾的是, 如果 CLID 值已變更、由中間或終止載波省略或截斷, Microsoft 幾乎無法 recourse 在公用電話網絡中修正這些問題。</span><span class="sxs-lookup"><span data-stu-id="b345b-112">Unfortunately, in the event the CLID value is changed, omitted or truncated by the intermediary or terminating carrier, Microsoft has little to no recourse in correcting such problems in the public telephone network.</span></span>

<span data-ttu-id="b345b-113">CNAM 中的不一致可能是由於中間或終止載波的延遲, 在授權資料庫中重新整理 CNAM 資訊, 就像在美國的情況下。</span><span class="sxs-lookup"><span data-stu-id="b345b-113">Inconsistencies in CNAM can be caused by delays in intermediate or terminating carriers refreshing CNAM info in authoritative databases as in the case of the United States.</span></span> <span data-ttu-id="b345b-114">在沒有 CNAM 的權威性資料庫的國家/地區中, 個別的運營商做法也可能會造成 CNAM 資訊在 tact 中與通話一起送達的問題。</span><span class="sxs-lookup"><span data-stu-id="b345b-114">In countries where there is no authoritative database for CNAM, individual carrier practices can also cause problems with CNAM information arriving in tact with the call.</span></span> <span data-ttu-id="b345b-115">Microsoft 目前不支援美國以外的國家/地區的來源 CNAM 資訊。」</span><span class="sxs-lookup"><span data-stu-id="b345b-115">Microsoft currently does not support originating CNAM information in countries other than the United States."</span></span>

## <a name="related-topics"></a><span data-ttu-id="b345b-116">相關主題</span><span class="sxs-lookup"><span data-stu-id="b345b-116">Related topics</span></span>


