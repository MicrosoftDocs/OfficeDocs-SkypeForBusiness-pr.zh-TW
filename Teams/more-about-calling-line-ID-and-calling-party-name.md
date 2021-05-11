---
title: 深入了解通話線路識別碼和來電方名稱
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: roykuntz, jenstr
ms.topic: article
ms.tgt.pltfrm: cloud
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business Online
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
ms.service: msteams
description: 瞭解通話線路識別碼和通話方名稱。
ms.openlocfilehash: dd68327c8fb3f63bf17e0736f9d41b727efc1ff8
ms.sourcegitcommit: 83f14c4c79559ef28357ff076938e52b369fc0c7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/10/2021
ms.locfileid: "52308312"
---
# <a name="more-about-calling-line-id-and-calling-party-name"></a><span data-ttu-id="1b4d7-103">深入了解通話線路識別碼和來電方名稱</span><span class="sxs-lookup"><span data-stu-id="1b4d7-103">More about Calling Line ID and Calling Party Name</span></span>

<span data-ttu-id="1b4d7-104">本機號碼包含兩個使用者面對的資訊：</span><span class="sxs-lookup"><span data-stu-id="1b4d7-104">CallerID consists of two user-facing pieces of information:</span></span>

- <span data-ttu-id="1b4d7-105">電話號碼 (稱為 CLID 或電話線識別碼) 。</span><span class="sxs-lookup"><span data-stu-id="1b4d7-105">A phone number (typically referred to as CLID or calling line ID).</span></span>

- <span data-ttu-id="1b4d7-106">通話方 (通常稱為 CNAM) 。</span><span class="sxs-lookup"><span data-stu-id="1b4d7-106">Calling party name (typically referred to as CNAM).</span></span> 

<span data-ttu-id="1b4d7-107">進行通話時，CLID (電話號碼) 會路由至目的地的電信 (也稱為終止電信) 。</span><span class="sxs-lookup"><span data-stu-id="1b4d7-107">When a call is made, the CLID (phone number) is routed to the destination's carrier (also known as the terminating carrier).</span></span> <span data-ttu-id="1b4d7-108">通話的 CNAM 資訊可能會或可能不會隨著通話路由，因為此資訊取決於國家/地區如何執行 CNAM (如果完全) 。</span><span class="sxs-lookup"><span data-stu-id="1b4d7-108">The CNAM information for the call may or may not be routed with the call because as this information depends on how the country has implemented CNAM (if at all).</span></span> <span data-ttu-id="1b4d7-109">CNAM 與通話的傳遞可靠性會因國家/地區以及處理電話的電信業者而不同 ，無論是作為仲介者或終止電信業者。</span><span class="sxs-lookup"><span data-stu-id="1b4d7-109">The reliability of CNAM delivery with the call varies depending on the country and carriers that handle the call--either as an intermediary or a terminating carrier.</span></span> 

<span data-ttu-id="1b4d7-110">CLID & CNAM 傳輸是終止電信者的責任。</span><span class="sxs-lookup"><span data-stu-id="1b4d7-110">CLID & CNAM transmission is the responsibility of the terminating carrier.</span></span> <span data-ttu-id="1b4d7-111">終止電信公司必須支援 CLID & CNAM 功能，並為這兩個值提供最新記錄。</span><span class="sxs-lookup"><span data-stu-id="1b4d7-111">The terminating carrier must support CLID & CNAM functionality as well as provide up-to-date records for both values.</span></span> <span data-ttu-id="1b4d7-112">當原始通話時，Microsoft 會可靠地提供 CLID 值，但這些值一旦通過中間電信業者或終止電信業者時，可能不會保持原狀。</span><span class="sxs-lookup"><span data-stu-id="1b4d7-112">Microsoft reliably provides CLID values when originating calls, but those values may not be kept intact once they pass through an intermediary carrier or the terminating carrier.</span></span> <span data-ttu-id="1b4d7-113">如果中間商或終止電信業者變更、省略或截斷 CLID 值，Microsoft 在修正公用電話網絡中這類問題方面幾乎無追索權。</span><span class="sxs-lookup"><span data-stu-id="1b4d7-113">If the CLID value is changed, omitted, or truncated by the intermediary or terminating carrier, Microsoft has little to no recourse in correcting such problems in the public telephone network.</span></span>

<span data-ttu-id="1b4d7-114">當中間端或終止電信公司延遲重新更新授權資料庫中的 CNAM 資訊時 ，CNAM 中的不一致可能會造成 ，就像美國的情況一樣。</span><span class="sxs-lookup"><span data-stu-id="1b4d7-114">Inconsistencies in CNAM can be caused when the intermediate or terminating carriers delay refreshing the CNAM information in authoritative databases--as in the case of the United States.</span></span> <span data-ttu-id="1b4d7-115">在還沒有 CNAM 授權資料庫的國家/地區，個別電信業者的做法也會造成 CNAM 資訊在通話中完整無缺的問題。</span><span class="sxs-lookup"><span data-stu-id="1b4d7-115">In countries where there are no authoritative databases for CNAM, individual carrier practices can also cause problems with CNAM information arriving intact with the call.</span></span> <span data-ttu-id="1b4d7-116">Microsoft 目前不支援美國外的國家/地區的原始 CNAM 資訊。</span><span class="sxs-lookup"><span data-stu-id="1b4d7-116">Microsoft currently does not support originating CNAM information in countries other than the United States.</span></span>

## <a name="related-topics"></a><span data-ttu-id="1b4d7-117">相關主題</span><span class="sxs-lookup"><span data-stu-id="1b4d7-117">Related topics</span></span>


