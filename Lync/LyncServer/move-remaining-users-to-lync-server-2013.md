---
title: 將剩餘使用者移到 Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Move remaining users to Lync Server 2013
ms:assetid: 72025e1b-97d1-40e9-8a98-28c018942b48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688090(v=OCS.15)
ms:contentKeyID: 49733689
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9d5c747a216ff5407a3150eb1cdcdfb94a3c73c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974770"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-remaining-users-to-lync-server-2013"></a><span data-ttu-id="feb68-102">將剩餘使用者移到 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="feb68-102">Move remaining users to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="feb68-103">_**主題上次修改日期：** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="feb68-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="feb68-104">您可以使用 Lync Server [控制台] 或 [Lync Server 管理命令介面]，將使用者移至新的 Lync Server 2013 部署。</span><span class="sxs-lookup"><span data-stu-id="feb68-104">You can move users to the new Lync Server 2013 deployment by using either Lync Server Control Panel or Lync Server Management Shell.</span></span> <span data-ttu-id="feb68-105">您必須符合一些需求，才能確保順利轉換至 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="feb68-105">You must meet some requirements to ensure a smooth transition to Lync Server 2013.</span></span> <span data-ttu-id="feb68-106">如需有關完成本主題中程式的先決條件的詳細資訊，請參閱[設定要遷移的用戶端](configure-clients-for-migration.md)。</span><span class="sxs-lookup"><span data-stu-id="feb68-106">For details about prerequisites to completing the procedures in this topic, see [Configure clients for migration](configure-clients-for-migration.md).</span></span> <span data-ttu-id="feb68-107">如需有關移動使用者的詳細步驟，請參閱[階段4：將測試使用者移至試驗池](phase-4-move-test-users-to-the-pilot-pool.md)。</span><span class="sxs-lookup"><span data-stu-id="feb68-107">For detailed steps about moving users, see [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="feb68-108">您無法使用 Active Directory 使用者和電腦管理單元或 Lync Server 2010 系統管理工具，將使用者從您的舊版環境移至 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="feb68-108">You cannot use the Active Directory Users and Computers snap-in or the Lync Server 2010 administrative tools to move users from your legacy environment to Lync Server 2013.</span></span>



</div>

<span data-ttu-id="feb68-109">當您將使用者移至 Lync Server 2013 池時，使用者的資料會移至與新的資料庫池相關聯的後端資料庫。</span><span class="sxs-lookup"><span data-stu-id="feb68-109">When you move a user to an Lync Server 2013 pool, the data for the user is moved to the back-end database that is associated with the new pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="feb68-110">這包括舊版使用者建立的作用中會議。</span><span class="sxs-lookup"><span data-stu-id="feb68-110">This includes the active meetings created by the legacy user.</span></span> <span data-ttu-id="feb68-111">例如，如果舊版使用者已設定「我的<STRONG>會議</STRONG>會議，則在使用者移動之後，新的 Lync Server 2013 池中仍會提供該會議。</span><span class="sxs-lookup"><span data-stu-id="feb68-111">For example, if a legacy user has configured a <STRONG>my meeting</STRONG> conference, that conference will still be available in the new Lync Server 2013 pool after the user has been moved.</span></span> <span data-ttu-id="feb68-112">存取該會議的詳細資料仍會是相同的<STRONG>會議 URL 與會議 ID</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="feb68-112">The details to access that meeting will still be the same <STRONG>conference URL and conference ID</STRONG>.</span></span> <span data-ttu-id="feb68-113">唯一的差異在於，該會議現在已託管在 Lync Server 2013 池中，而不是在 Lync Server 2010 池中。</span><span class="sxs-lookup"><span data-stu-id="feb68-113">The only difference is that the conference is now hosted in the Lync Server 2013 pool, and not in the Lync Server 2010 pool.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="feb68-114">在 Lync Server 2013 上託管使用者並不需要您同時部署已升級的用戶端。</span><span class="sxs-lookup"><span data-stu-id="feb68-114">Homing users on Lync Server 2013 does not require that you deploy upgraded clients at the same time.</span></span> <span data-ttu-id="feb68-115">只有在使用者升級至新的用戶端軟體時，才能使用新的功能。</span><span class="sxs-lookup"><span data-stu-id="feb68-115">New functionality will be available to users only when they have upgraded to the new client software.</span></span>



</div>

<div>

## <a name="post-migration-task"></a><span data-ttu-id="feb68-116">遷移後任務</span><span class="sxs-lookup"><span data-stu-id="feb68-116">Post Migration Task</span></span>

1.  <span data-ttu-id="feb68-117">在您移動使用者之後，請確認指派給他們的會議原則。</span><span class="sxs-lookup"><span data-stu-id="feb68-117">After you move users, verify the conferencing policy that is assigned to them.</span></span>

2.  <span data-ttu-id="feb68-118">若要確保由駐留在 Lync Server 2013 的使用者組織的會議能與駐留在 Lync Server 2010 的聯盟使用者順暢運作，指派給已遷移使用者的會議原則應該允許匿名參與者。</span><span class="sxs-lookup"><span data-stu-id="feb68-118">To ensure that meetings organized by users homed on Lync Server 2013 work seamlessly with federated users who are homed on Lync Server 2010, the conferencing policy assigned to the migrated users should allow anonymous participants.</span></span>

3.  <span data-ttu-id="feb68-119">允許匿名參與者的會議原則**允許參與者邀請**lync server 2013 [控制台] 中選取的匿名使用者，並在 Lync Server 管理命令介面的 [ **CsConferencingPolicy** ] Cmdlet 的輸出中，將**AllowAnonymousParticipantsInMeetings**設為**True** 。</span><span class="sxs-lookup"><span data-stu-id="feb68-119">Conferencing policies that allow anonymous participants have **Allow participants to invite anonymous users** selected in Lync Server 2013 Control Panel and have **AllowAnonymousParticipantsInMeetings** set to **True** in the output from the **Get-CsConferencingPolicy** cmdlet in the Lync Server Management Shell.</span></span>

4.  <span data-ttu-id="feb68-120">如需使用 Lync Server 管理命令介面設定會議原則的詳細資訊，請參閱 Lync Server 管理命令介面檔中的[設定 CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) 。</span><span class="sxs-lookup"><span data-stu-id="feb68-120">For details about configuring conferencing policy by using Lync Server Management Shell, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) in the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

