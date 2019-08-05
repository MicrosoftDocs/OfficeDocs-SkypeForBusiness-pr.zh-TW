---
title: 遷移現有的會議與會議內容
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: '當使用者帳戶移至商務用 Skype Server 2019 伺服器時, 下列資訊就會與該使用者帳戶一起移動:'
ms.openlocfilehash: 4b5c7981374f3e2bf6dc2d87a0b21d972ddb14ae
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191146"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a><span data-ttu-id="3323b-103">遷移現有的會議與會議內容</span><span class="sxs-lookup"><span data-stu-id="3323b-103">Migrate existing meetings and meeting content</span></span>

<span data-ttu-id="3323b-104">當使用者帳戶移至商務用 Skype Server 2019 伺服器時, 下列資訊會與該使用者帳戶一起移動:</span><span class="sxs-lookup"><span data-stu-id="3323b-104">When a user account is moved to a Skype for Business Server 2019 server, the following information is moved with that user account:</span></span>
  
- <span data-ttu-id="3323b-105">**已由使用者排程的會議**。</span><span class="sxs-lookup"><span data-stu-id="3323b-105">**Meetings already scheduled by the user**.</span></span> <span data-ttu-id="3323b-106">這包括移動會議目錄及會議資料。</span><span class="sxs-lookup"><span data-stu-id="3323b-106">This includes moving the conferencing directories and conferencing data.</span></span>
    
- <span data-ttu-id="3323b-107">**使用者的個人身分識別號碼 (PIN)**。</span><span class="sxs-lookup"><span data-stu-id="3323b-107">**User's personal identification number (PIN)**.</span></span> <span data-ttu-id="3323b-108">使用者目前的 PIN 會持續起作用, 直到過期為止, 或使用者要求新的 PIN。</span><span class="sxs-lookup"><span data-stu-id="3323b-108">The user's current PIN continues to work until it expires or the user requests a new PIN.</span></span>
    
<span data-ttu-id="3323b-109">下列使用者帳戶資訊不會移至新的伺服器。</span><span class="sxs-lookup"><span data-stu-id="3323b-109">The following user account information does not move to the new server.</span></span>
  
- <span data-ttu-id="3323b-110">**會議內容**。</span><span class="sxs-lookup"><span data-stu-id="3323b-110">**Meeting content**.</span></span> <span data-ttu-id="3323b-111">若要移動在會議期間共用的內容 (例如 PowerPoint、白板、附件或投票資料), 請使用 **-MoveConferenceData**參數做為**move-csuser** Cmdlet 的一部分。</span><span class="sxs-lookup"><span data-stu-id="3323b-111">In order to move the content shared during a meeting, such as PowerPoint, Whiteboard, attachments, or poll data, use the **-MoveConferenceData** parameter as part of the **Move-CsUser** cmdlet.</span></span> 
    

