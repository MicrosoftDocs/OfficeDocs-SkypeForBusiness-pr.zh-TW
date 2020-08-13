---
title: 刪除網站或使用者群組的電話撥入式會議 PIN 設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete dial-in conferencing PIN settings for a site or group of users
ms:assetid: 15a9faee-d024-4c0e-b2a0-fe7e7dc00589
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520955(v=OCS.15)
ms:contentKeyID: 48183498
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a085da7207bcccbe6a1a1d8009fb3f054e20dfbb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202549"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users-in-lync-server-2013"></a><span data-ttu-id="bfbd2-102">在 Lync Server 2013 中刪除網站或使用者群組的電話撥入式會議 PIN 設定</span><span class="sxs-lookup"><span data-stu-id="bfbd2-102">Delete dial-in conferencing PIN settings for a site or group of users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bfbd2-103">_**主題上次修改日期：** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="bfbd2-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="bfbd2-104">遵循下列步驟可以刪除使用者層級或網站層級 PIN 原則。</span><span class="sxs-lookup"><span data-stu-id="bfbd2-104">Follow these steps to delete a user-level or a site-level PIN policy.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="bfbd2-105">您無法刪除全域 PIN 原則。</span><span class="sxs-lookup"><span data-stu-id="bfbd2-105">You cannot delete the global PIN policy.</span></span>



</div>

<div>

## <a name="to-delete-a-user-or-site-pin-policy"></a><span data-ttu-id="bfbd2-106">刪除使用者或網站 PIN 原則</span><span class="sxs-lookup"><span data-stu-id="bfbd2-106">To delete a user or site PIN policy</span></span>

1.  <span data-ttu-id="bfbd2-107">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您已部署 Lync Server 2013 之網路中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="bfbd2-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="bfbd2-108">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="bfbd2-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="bfbd2-109">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="bfbd2-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="bfbd2-110">在左導覽列中，按一下 [會議]\*\*\*\* 再按一下 [PIN 原則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bfbd2-110">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>

4.  <span data-ttu-id="bfbd2-111">在 **[PIN 原則]** 頁面中的搜尋欄位，輸入您要刪除之原則的全部或部分名稱。</span><span class="sxs-lookup"><span data-stu-id="bfbd2-111">On the **PIN Policy** page, in the search field, type all or part of the name of the policy you want to delete.</span></span>

5.  <span data-ttu-id="bfbd2-112">在原則清單中，按一下您要的原則，再按一下 **[編輯]**，然後按一下 **[刪除]**。</span><span class="sxs-lookup"><span data-stu-id="bfbd2-112">In the list of policies, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="bfbd2-113">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bfbd2-113">Click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

