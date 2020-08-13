---
title: 將剩餘的使用者移至 Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move remaining users to Lync Server 2013
ms:assetid: 72025e1b-97d1-40e9-8a98-28c018942b48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688090(v=OCS.15)
ms:contentKeyID: 49733689
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e01f5b0fb07477437de9af2acd7ad58e946e6c32
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189786"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-remaining-users-to-lync-server-2013"></a><span data-ttu-id="be3aa-102">將剩餘的使用者移至 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="be3aa-102">Move remaining users to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="be3aa-103">_**主題上次修改日期：** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="be3aa-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="be3aa-104">您可以使用 Lync Server 控制台或 Lync Server 管理命令介面，將使用者移至新的 Lync Server 2013 部署。</span><span class="sxs-lookup"><span data-stu-id="be3aa-104">You can move users to the new Lync Server 2013 deployment by using either Lync Server Control Panel or Lync Server Management Shell.</span></span> <span data-ttu-id="be3aa-105">您必須符合某些需求，以確保順利轉換至 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="be3aa-105">You must meet some requirements to ensure a smooth transition to Lync Server 2013.</span></span> <span data-ttu-id="be3aa-106">如需完成本主題中程式之必要條件的詳細資訊，請參閱[設定用戶端進行遷移](configure-clients-for-migration.md)。</span><span class="sxs-lookup"><span data-stu-id="be3aa-106">For details about prerequisites to completing the procedures in this topic, see [Configure clients for migration](configure-clients-for-migration.md).</span></span> <span data-ttu-id="be3aa-107">如需移動使用者的詳細步驟，請參閱[第4階段：將測試使用者移至試驗集](phase-4-move-test-users-to-the-pilot-pool.md)區。</span><span class="sxs-lookup"><span data-stu-id="be3aa-107">For detailed steps about moving users, see [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="be3aa-108">您無法使用 Active Directory 使用者及電腦嵌入式管理單元或 Lync Server 2010 系統管理工具，將使用者從舊版環境移至 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="be3aa-108">You cannot use the Active Directory Users and Computers snap-in or the Lync Server 2010 administrative tools to move users from your legacy environment to Lync Server 2013.</span></span>



</div>

<span data-ttu-id="be3aa-109">當您將使用者移至 Lync Server 2013 集區時，使用者的資料會移至與新集區相關聯的後端資料庫。</span><span class="sxs-lookup"><span data-stu-id="be3aa-109">When you move a user to an Lync Server 2013 pool, the data for the user is moved to the back-end database that is associated with the new pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="be3aa-110">這包括由舊使用者所建立之作用中的會議。</span><span class="sxs-lookup"><span data-stu-id="be3aa-110">This includes the active meetings created by the legacy user.</span></span> <span data-ttu-id="be3aa-111">例如，如果舊版使用者已設定「我的<STRONG>會議</STRONG>會議」，該會議在使用者移動之後仍會在新的 Lync Server 2013 集區中使用。</span><span class="sxs-lookup"><span data-stu-id="be3aa-111">For example, if a legacy user has configured a <STRONG>my meeting</STRONG> conference, that conference will still be available in the new Lync Server 2013 pool after the user has been moved.</span></span> <span data-ttu-id="be3aa-112">存取該會議的詳細資料仍為相同的 <STRONG>[會議 URL 及會議 ID]</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="be3aa-112">The details to access that meeting will still be the same <STRONG>conference URL and conference ID</STRONG>.</span></span> <span data-ttu-id="be3aa-113">唯一的差別在於會議現在是主控于 Lync Server 2013 集區，而不是 Lync Server 2010 集區。</span><span class="sxs-lookup"><span data-stu-id="be3aa-113">The only difference is that the conference is now hosted in the Lync Server 2013 pool, and not in the Lync Server 2010 pool.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="be3aa-114">在 Lync Server 2013 上執行使用者，不需要同時部署已升級的用戶端。</span><span class="sxs-lookup"><span data-stu-id="be3aa-114">Homing users on Lync Server 2013 does not require that you deploy upgraded clients at the same time.</span></span> <span data-ttu-id="be3aa-115">只有當使用者已升級為新的用戶端軟體時，才可使用新功能。</span><span class="sxs-lookup"><span data-stu-id="be3aa-115">New functionality will be available to users only when they have upgraded to the new client software.</span></span>



</div>

<div>

## <a name="post-migration-task"></a><span data-ttu-id="be3aa-116">移轉後的工作</span><span class="sxs-lookup"><span data-stu-id="be3aa-116">Post Migration Task</span></span>

1.  <span data-ttu-id="be3aa-117">一旦移除使用者之後，請驗證指派給他們的會議原則。</span><span class="sxs-lookup"><span data-stu-id="be3aa-117">After you move users, verify the conferencing policy that is assigned to them.</span></span>

2.  <span data-ttu-id="be3aa-118">為了確保以 Lync Server 2013 組織的使用者所組織的會議能夠與駐留在 Lync Server 2010 的同盟使用者順利運作，指派給已遷移使用者的會議原則應該允許匿名參與者。</span><span class="sxs-lookup"><span data-stu-id="be3aa-118">To ensure that meetings organized by users homed on Lync Server 2013 work seamlessly with federated users who are homed on Lync Server 2010, the conferencing policy assigned to the migrated users should allow anonymous participants.</span></span>

3.  <span data-ttu-id="be3aa-119">允許匿名參與者的會議原則**允許參與者邀請**lync Server 2013 控制台中所選取的匿名使用者，而且**AllowAnonymousParticipantsInMeetings**在 lync server 管理命令介面中從**Get-CsConferencingPolicy** Cmdlet 的輸出中，設定為**True** 。</span><span class="sxs-lookup"><span data-stu-id="be3aa-119">Conferencing policies that allow anonymous participants have **Allow participants to invite anonymous users** selected in Lync Server 2013 Control Panel and have **AllowAnonymousParticipantsInMeetings** set to **True** in the output from the **Get-CsConferencingPolicy** cmdlet in the Lync Server Management Shell.</span></span>

4.  <span data-ttu-id="be3aa-120">如需使用 Lync Server 管理命令介面設定會議原則的詳細資訊，請參閱 Lync Server 管理命令介面檔中的[CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) 。</span><span class="sxs-lookup"><span data-stu-id="be3aa-120">For details about configuring conferencing policy by using Lync Server Management Shell, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) in the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

