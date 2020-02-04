---
title: 移轉現有的會議與會議內容
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate existing meetings and meeting content
ms:assetid: 30516731-2ae1-4a6d-a7e1-d3f05778c954
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688011(v=OCS.15)
ms:contentKeyID: 49733599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0aa0b83e2e206421300d16faf220b3fa0bb81503
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762921"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-existing-meetings-and-meeting-content"></a><span data-ttu-id="41b77-102">移轉現有的會議與會議內容</span><span class="sxs-lookup"><span data-stu-id="41b77-102">Migrate existing meetings and meeting content</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41b77-103">_**主題上次修改日期：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="41b77-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="41b77-104">當使用者帳戶從 Lync Server 2010 移至 Lync Server 2013 伺服器時，下列資訊會與該使用者帳戶一起移動：</span><span class="sxs-lookup"><span data-stu-id="41b77-104">When a user account is moved from Lync Server 2010 to a Lync Server 2013 server, the following information is moved with that user account:</span></span>

  - <span data-ttu-id="41b77-105">**已由使用者排程的會議**。</span><span class="sxs-lookup"><span data-stu-id="41b77-105">**Meetings already scheduled by the user**.</span></span> <span data-ttu-id="41b77-106">這包括移動會議目錄及會議資料。</span><span class="sxs-lookup"><span data-stu-id="41b77-106">This includes moving the conferencing directories and conferencing data.</span></span>

  - <span data-ttu-id="41b77-107">**使用者的個人身分識別號碼（PIN）**。</span><span class="sxs-lookup"><span data-stu-id="41b77-107">**User’s personal identification number (PIN)**.</span></span> <span data-ttu-id="41b77-108">使用者目前的 PIN 會持續起作用，直到過期為止，或使用者要求新的 PIN。</span><span class="sxs-lookup"><span data-stu-id="41b77-108">The user’s current PIN continues to work until it expires or the user requests a new PIN.</span></span>

<span data-ttu-id="41b77-109">下列使用者帳戶資訊不會移至新的伺服器。</span><span class="sxs-lookup"><span data-stu-id="41b77-109">The following user account information does not move to the new server.</span></span>

  - <span data-ttu-id="41b77-110">**會議內容**。</span><span class="sxs-lookup"><span data-stu-id="41b77-110">**Meeting content**.</span></span> <span data-ttu-id="41b77-111">若要移動在會議期間共用的內容（例如 PowerPoint、白板、附件或投票資料），請使用 **-MoveConferenceData**參數做為**move-csuser** Cmdlet 的一部分。</span><span class="sxs-lookup"><span data-stu-id="41b77-111">In order to move the content shared during a meeting, for example PowerPoint, Whiteboard, attachments or poll data, use the **-MoveConferenceData** parameter as part of the **Move-CsUser** cmdlet.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

