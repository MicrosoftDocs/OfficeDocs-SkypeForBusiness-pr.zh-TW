---
title: Lync Server 2013：設定電話撥入式會議存取號碼
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure dial-in conferencing access numbers
ms:assetid: d8a18030-f318-43dd-834d-70e5014b5e8a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398952(v=OCS.15)
ms:contentKeyID: 48185623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83c7069db95d36e79d74cea81faf3aa98685832f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504770"
---
# <a name="configure-dial-in-conferencing-access-numbers-in-lync-server-2013"></a><span data-ttu-id="c53fb-102">在 Lync Server 2013 中設定電話撥入式會議存取號碼</span><span class="sxs-lookup"><span data-stu-id="c53fb-102">Configure dial-in conferencing access numbers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c53fb-103">_**主題上次修改日期：** 2011-07-17_</span><span class="sxs-lookup"><span data-stu-id="c53fb-103">_**Topic Last Modified:** 2011-07-17_</span></span>

<span data-ttu-id="c53fb-104">當您部署電話撥入式會議時，您必須設定使用者可以從公用交換電話網路 (PSTN) 撥打的電話號碼，以加入會議的音訊部分。</span><span class="sxs-lookup"><span data-stu-id="c53fb-104">When you deploy dial-in conferencing, you need to set up phone numbers that users can dial from the public switched telephone network (PSTN) to join the audio portion of conferences.</span></span> <span data-ttu-id="c53fb-105">這些撥入存取號碼會顯示在會議邀請和電話撥入式會議設定網頁上。</span><span class="sxs-lookup"><span data-stu-id="c53fb-105">These dial-in access numbers appear in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>

<span data-ttu-id="c53fb-106">在您可以建立撥入存取號碼之前，您必須先規劃撥入式會議區域，然後使用地區設定撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="c53fb-106">Before you can create dial-in access numbers, you must first plan your dial-in conferencing regions and then configure dial plans with the regions.</span></span> <span data-ttu-id="c53fb-107">如需地區的詳細資訊，請參閱規劃檔中的 [Lync Server 2013 中的電話撥入式會議需求](lync-server-2013-dial-in-conferencing-requirements.md) 。</span><span class="sxs-lookup"><span data-stu-id="c53fb-107">For details about regions, see [Dial-in conferencing requirements in Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) in the Planning documentation.</span></span> <span data-ttu-id="c53fb-108">如需設定電話撥入式會議的撥號對應表的詳細資訊，請參閱 [在 Lync Server 2013 中設定電話撥入式會議的撥號](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)對應表。</span><span class="sxs-lookup"><span data-stu-id="c53fb-108">For details about configuring dial plans for dial-in conferencing, see [Configure dial plans for dial-in conferencing in Lync Server 2013](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c53fb-109">您無法使用新的撥入存取號碼，除非 Active Directory 網域服務 (AD &nbsp; DS) 該存取號碼的複寫已完成。</span><span class="sxs-lookup"><span data-stu-id="c53fb-109">You cannot use a new dial-in access number until Active Directory Domain Services (AD&nbsp;DS) replication of that access number is complete.</span></span> <span data-ttu-id="c53fb-110">複寫可能需要數小時才能完成。</span><span class="sxs-lookup"><span data-stu-id="c53fb-110">Replication can take several hours to complete.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="c53fb-111">在您建立撥入存取號碼之後，您可以修改 Active Directory 連絡人物件的顯示名稱，讓使用者可以更輕鬆地識別正確的存取號碼。</span><span class="sxs-lookup"><span data-stu-id="c53fb-111">After you create dial-in access numbers, you can modify the display name for the Active Directory contact objects so that users can more easily identify the correct access number.</span></span> <span data-ttu-id="c53fb-112">使用 <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> Cmdlet 可修改顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="c53fb-112">Use the <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> cmdlet to modify the display name.</span></span> <span data-ttu-id="c53fb-113">您不應該手動修改 Active Directory 物件。</span><span class="sxs-lookup"><span data-stu-id="c53fb-113">You should not modify Active Directory objects manually.</span></span> <span data-ttu-id="c53fb-114">如需修改存取號碼的詳細資訊，請參閱 <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> Cmdlet 的 Lync Server 管理命令介面檔。</span><span class="sxs-lookup"><span data-stu-id="c53fb-114">For details about modifying an access number, see Lync Server Management Shell documentation for the <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> cmdlet.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c53fb-115">本章節內容</span><span class="sxs-lookup"><span data-stu-id="c53fb-115">In This Section</span></span>

[<span data-ttu-id="c53fb-116">在 Lync Server 2013 中建立或修改電話撥入式會議存取號碼</span><span class="sxs-lookup"><span data-stu-id="c53fb-116">Create or modify a dial-in conferencing access number in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-dial-in-conferencing-access-number.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c53fb-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c53fb-117">See Also</span></span>


[<span data-ttu-id="c53fb-118">Lync Server 2013 中的電話撥入式會議需求</span><span class="sxs-lookup"><span data-stu-id="c53fb-118">Dial-in conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-requirements.md)  


[<span data-ttu-id="c53fb-119">在 Lync Server 2013 中設定電話撥入式會議的撥號對應表</span><span class="sxs-lookup"><span data-stu-id="c53fb-119">Configure dial plans for dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

