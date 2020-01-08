---
title: Lync Server 2013：修改預設電話撥入式會議 PIN 設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify the default dial-in conferencing PIN settings
ms:assetid: 2d110e94-ad29-4755-b17f-d8c2da9b78a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425780(v=OCS.15)
ms:contentKeyID: 48183712
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ee196fae24ba4a6b7bf8e0ede0bbc0b35a7b3fc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976006"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-default-dial-in-conferencing-pin-settings-in-lync-server-2013"></a><span data-ttu-id="3a3c1-102">在 Lync Server 2013 中修改預設電話撥入式會議 PIN 設定</span><span class="sxs-lookup"><span data-stu-id="3a3c1-102">Modify the default dial-in conferencing PIN settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3a3c1-103">_**主題上次修改日期：** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="3a3c1-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="3a3c1-104">全域 PIN 原則會定義目錄林層級電話撥入式會議 Pin 的規則。</span><span class="sxs-lookup"><span data-stu-id="3a3c1-104">The global PIN policy defines the rules for dial-in conferencing PINs at the forest level.</span></span> <span data-ttu-id="3a3c1-105">請依照這些步驟來修改全域電話撥入式會議 PIN 原則原則。</span><span class="sxs-lookup"><span data-stu-id="3a3c1-105">Follow these steps to modify the global dial-in conferencing PIN policy.</span></span> <span data-ttu-id="3a3c1-106">如需在網站或使用者層級建立或修改電話撥入式會議 PIN 原則的詳細資料，請參閱[在 Lync Server 2013 中為網站或使用者群組建立或修改電話撥入式會議 pin 設定](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md)。</span><span class="sxs-lookup"><span data-stu-id="3a3c1-106">For details about creating or modifying a dial-in conferencing PIN policy at the site or user level, see [Create or modify dial-in conferencing PIN settings in Lync Server 2013 for a site or group of users](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md).</span></span>

<div>

## <a name="to-modify-the-global-pin-policy"></a><span data-ttu-id="3a3c1-107">修改全域 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="3a3c1-107">To modify the global PIN policy</span></span>

1.  <span data-ttu-id="3a3c1-108">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您在其中部署 Lync Server 2013 的網路中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="3a3c1-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="3a3c1-109">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="3a3c1-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3a3c1-110">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="3a3c1-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3a3c1-111">在左側導覽列中，按一下 [**會議**]，然後按一下 [ **PIN 規則**]。</span><span class="sxs-lookup"><span data-stu-id="3a3c1-111">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>

4.  <span data-ttu-id="3a3c1-112">在 [ **PIN 原則**] 頁面上，按一下 [**全域**原則]，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="3a3c1-112">On the **PIN Policy** page, click the **Global** policy, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="3a3c1-113">在 [**編輯 Pin 原則**] 的 [**最小 pin 長度**] 中，輸入或選取您要允許的最小 pin 長度。</span><span class="sxs-lookup"><span data-stu-id="3a3c1-113">In **Edit PIN Policy**, in **Minimum PIN length**, type or select the minimum PIN length that you want to allow.</span></span> <span data-ttu-id="3a3c1-114">預設的最小長度為5位數。</span><span class="sxs-lookup"><span data-stu-id="3a3c1-114">The default minimum length is five digits.</span></span>

6.  <span data-ttu-id="3a3c1-115">若要在封鎖使用者之前，能夠指定最大的登入嘗試次數，請選取 [**指定最大登入嘗試**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="3a3c1-115">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box.</span></span> <span data-ttu-id="3a3c1-116">如果您沒有選取此選項，則會根據 PIN 長度自動判斷允許的最大嘗試次數上限。</span><span class="sxs-lookup"><span data-stu-id="3a3c1-116">If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length.</span></span> <span data-ttu-id="3a3c1-117">根據預設，會自動決定最大嘗試次數。</span><span class="sxs-lookup"><span data-stu-id="3a3c1-117">By default, the maximum number of attempts is automatically determined.</span></span>

7.  <span data-ttu-id="3a3c1-118">如果您已選取 [**指定最大登入嘗試**] 核取方塊，請在 [**最大登入次數**] 中，輸入或選取您要允許的最大登入嘗試次數。</span><span class="sxs-lookup"><span data-stu-id="3a3c1-118">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>

8.  <span data-ttu-id="3a3c1-119">若要讓 Pin 到期，請選取 [**啟用 PIN 到期**日] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="3a3c1-119">To have PINs expire, select the **Enable PIN expiration** check box.</span></span> <span data-ttu-id="3a3c1-120">如果您沒有選取此選項，針腳將永不過期。</span><span class="sxs-lookup"><span data-stu-id="3a3c1-120">If you do not select this option, PINs will never expire.</span></span> <span data-ttu-id="3a3c1-121">根據預設，Pin 永遠不會過期。</span><span class="sxs-lookup"><span data-stu-id="3a3c1-121">By default, PINs never expire.</span></span>

9.  <span data-ttu-id="3a3c1-122">如果您已選取 [**啟用 PIN 到期**日] 核取方塊，請在 **[PIN 到期日之後（天數）**] 中，輸入或選取 pin 到期前的天數。</span><span class="sxs-lookup"><span data-stu-id="3a3c1-122">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>

10. <span data-ttu-id="3a3c1-123">在 [ **PIN 記錄計數**] 中，輸入使用者必須建立才能重複使用 pin 的 pin 數。</span><span class="sxs-lookup"><span data-stu-id="3a3c1-123">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN.</span></span> <span data-ttu-id="3a3c1-124">根據預設，使用者可以重複使用他們的 Pin。</span><span class="sxs-lookup"><span data-stu-id="3a3c1-124">By default, users can reuse their PINs.</span></span>

11. <span data-ttu-id="3a3c1-125">若要在 Pin 中允許通用位數（例如順序編號和重複的數位組），請選取 [**允許常見模式**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="3a3c1-125">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box.</span></span> <span data-ttu-id="3a3c1-126">如果您沒有選取此選項，則只允許使用複雜的數位模式。</span><span class="sxs-lookup"><span data-stu-id="3a3c1-126">If you do not select this option, only complex patterns of digits are allowed.</span></span> <span data-ttu-id="3a3c1-127">根據預設，只允許使用複雜的數位模式。</span><span class="sxs-lookup"><span data-stu-id="3a3c1-127">By default, only complex patterns of digits are allowed.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="3a3c1-128">我們建議您不要允許通用模式。</span><span class="sxs-lookup"><span data-stu-id="3a3c1-128">We recommend that you do not allow common patterns.</span></span>

    
    </div>

12. <span data-ttu-id="3a3c1-129">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3a3c1-129">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

