---
title: 將剩餘使用者移到 Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move remaining users to Lync Server 2013
ms:assetid: 0eb990f0-f720-47a7-aaee-437fbd4c4c33
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687968(v=OCS.15)
ms:contentKeyID: 49733554
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bcb5a709e896b66a1c8cd33a930bfeed5e05644f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743733"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-remaining-users-to-lync-server-2013"></a><span data-ttu-id="a4788-102">將剩餘使用者移到 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a4788-102">Move remaining users to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a4788-103">_**主題上次修改日期：** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="a4788-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="a4788-104">您可以使用 Lync Server [控制台] 或 [Lync Server 管理命令介面]，將使用者移至新的 Lync Server 2013 部署。</span><span class="sxs-lookup"><span data-stu-id="a4788-104">You can move users to the new Lync Server 2013 deployment by using either Lync Server Control Panel or Lync Server Management Shell.</span></span> <span data-ttu-id="a4788-105">您必須符合一些需求，才能確保順利轉換至 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="a4788-105">You must meet some requirements to ensure a smooth transition to Lync Server 2013.</span></span> <span data-ttu-id="a4788-106">如需有關完成本主題中程式的先決條件的詳細資訊，請參閱[設定要遷移的用戶端](configure-clients-for-migration_1.md)。</span><span class="sxs-lookup"><span data-stu-id="a4788-106">For details about prerequisites to completing the procedures in this topic, see [Configure clients for migration](configure-clients-for-migration_1.md).</span></span> <span data-ttu-id="a4788-107">如需有關移動使用者的詳細步驟，請參閱[階段6：將使用者移至試驗](phase-6-move-users-to-the-pilot-pool.md)區。</span><span class="sxs-lookup"><span data-stu-id="a4788-107">For detailed steps about moving users, see [Phase 6: Move users to the pilot pool](phase-6-move-users-to-the-pilot-pool.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a4788-108">您無法使用 Active Directory 使用者和電腦的管理單元或 Microsoft Office 通訊伺服器 2007 R2 管理工具，將使用者從您的舊版環境移至 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="a4788-108">You cannot use the Active Directory Users and Computers snap-in or the Microsoft Office Communications Server 2007 R2 administrative tools to move users from your legacy environment to Lync Server 2013.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a4788-109"><STRONG>CsLegacyUser</STRONG> Cmdlet 需要正確地形成使用者名稱，且沒有前導或尾部空格。</span><span class="sxs-lookup"><span data-stu-id="a4788-109">The <STRONG>Move-CsLegacyUser</STRONG> cmdlet requires that user names are properly formed and do not have leading or trailing spaces.</span></span> <span data-ttu-id="a4788-110">如果使用者帳戶包含前置或尾部空格，就無法使用<STRONG>CsLegacyUser</STRONG> Cmdlet 移動。</span><span class="sxs-lookup"><span data-stu-id="a4788-110">You cannot move a user account using the <STRONG>Move-CsLegacyUser</STRONG> cmdlet if it contains leading or trailing spaces.</span></span>



</div>

<span data-ttu-id="a4788-111">當您將使用者移至 Lync Server 2013 池時，使用者的資料會移至與新的資料庫池相關聯的後端資料庫。</span><span class="sxs-lookup"><span data-stu-id="a4788-111">When you move a user to an Lync Server 2013 pool, the data for the user is moved to the back-end database that is associated with the new pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a4788-112">這包括舊版使用者建立的作用中會議。</span><span class="sxs-lookup"><span data-stu-id="a4788-112">This includes the active meetings created by the legacy user.</span></span> <span data-ttu-id="a4788-113">例如，如果舊版使用者已設定「我的<STRONG>會議</STRONG>會議，則在使用者移動之後，仍可在新的 Lync Server 2013 池中提供該會議。</span><span class="sxs-lookup"><span data-stu-id="a4788-113">For example, if a legacy user has configured a <STRONG>my meeting</STRONG> conference, that conference will still be available in the new Lync Server 2013 pool, after the user has been moved.</span></span> <span data-ttu-id="a4788-114">存取該會議的詳細資料仍會是相同的<STRONG>會議 URL 與會議 ID</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="a4788-114">The details to access that meeting will still be the same <STRONG>conference URL and conference ID</STRONG>.</span></span> <span data-ttu-id="a4788-115">唯一的差異在於，該會議現在已託管在 Lync Server 2013 池中，而不是在 Office 通訊伺服器 2007 R2 池中。</span><span class="sxs-lookup"><span data-stu-id="a4788-115">The only difference is that the conference is now hosted in the Lync Server 2013 pool, and not in Office Communications Server 2007 R2 pool.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="a4788-116">在 Lync Server 2013 上託管使用者並不需要您同時部署已升級的用戶端。</span><span class="sxs-lookup"><span data-stu-id="a4788-116">Homing users on Lync Server 2013 does not require that you deploy upgraded clients at the same time.</span></span> <span data-ttu-id="a4788-117">只有在使用者升級至新的用戶端軟體時，才能使用新的功能。</span><span class="sxs-lookup"><span data-stu-id="a4788-117">New functionality will be available to users only when they have upgraded to the new client software.</span></span>



</div>

<div>

## <a name="post-migration-task"></a><span data-ttu-id="a4788-118">遷移後任務</span><span class="sxs-lookup"><span data-stu-id="a4788-118">Post Migration Task</span></span>

1.  <span data-ttu-id="a4788-119">在您移動使用者之後，請確認指派給他們的會議原則。</span><span class="sxs-lookup"><span data-stu-id="a4788-119">After you move users, verify the conferencing policy that is assigned to them.</span></span>

2.  <span data-ttu-id="a4788-120">若要確保由駐留在 Lync Server 2013 的使用者所組織的會議能與駐留在 Office 通訊伺服器 2007 R2 的同盟使用者順暢運作，指派給已遷移使用者的會議原則應該允許匿名參與者。</span><span class="sxs-lookup"><span data-stu-id="a4788-120">To ensure that meetings organized by users homed on Lync Server 2013 work seamlessly with federated users who are homed on Office Communications Server 2007 R2, the conferencing policy assigned to the migrated users should allow anonymous participants.</span></span>

3.  <span data-ttu-id="a4788-121">允許匿名參與者的會議原則**允許參與者邀請**lync server 2013 [控制台] 中選取的匿名使用者，並在 Lync Server 管理命令介面的 [ **CsConferencingPolicy** ] Cmdlet 的輸出中，將**AllowAnonymousParticipantsInMeetings**設為**True** 。</span><span class="sxs-lookup"><span data-stu-id="a4788-121">Conferencing policies that allow anonymous participants have **Allow participants to invite anonymous users** selected in Lync Server 2013 Control Panel and have **AllowAnonymousParticipantsInMeetings** set to **True** in the output from the **Get-CsConferencingPolicy** cmdlet in the Lync Server Management Shell.</span></span>

4.  <span data-ttu-id="a4788-122">如需使用 Lync Server 管理命令介面設定會議原則的詳細資訊，請參閱 Lync Server 管理命令介面檔中的[設定 CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) 。</span><span class="sxs-lookup"><span data-stu-id="a4788-122">For details about configuring conferencing policy by using Lync Server Management Shell, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) in the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

