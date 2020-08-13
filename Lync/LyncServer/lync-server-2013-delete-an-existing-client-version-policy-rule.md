---
title: Lync Server 2013：刪除現有的用戶端版本原則規則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing client version policy rule
ms:assetid: 2fe351c4-d78b-47d5-af49-d47ee5e0fe42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ923066(v=OCS.15)
ms:contentKeyID: 50675352
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f828132c35fb81b413ce1f46577efaf7ee09541d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202759"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-client-version-policy-rule-in-lync-server-2013"></a><span data-ttu-id="10934-102">在 Lync Server 2013 中刪除現有的用戶端版本原則規則</span><span class="sxs-lookup"><span data-stu-id="10934-102">Delete an existing client version policy rule in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="10934-103">_**主題上次修改日期：** 2013-01-21_</span><span class="sxs-lookup"><span data-stu-id="10934-103">_**Topic Last Modified:** 2013-01-21_</span></span>

<span data-ttu-id="10934-104">用戶端版本原則是由一組用戶端版本原則規則所組成。</span><span class="sxs-lookup"><span data-stu-id="10934-104">A client version policy is made up of a set of client version policy rules.</span></span> <span data-ttu-id="10934-105">當使用者嘗試以特定用戶端及用戶端版本登入時，這些規則會定義所要採取的動作。</span><span class="sxs-lookup"><span data-stu-id="10934-105">These rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span> <span data-ttu-id="10934-106">您可以從 Lync Server 2013 控制台中刪除用戶端版本原則中的個別規則。</span><span class="sxs-lookup"><span data-stu-id="10934-106">You can delete individual rules from a client version policy from Lync Server 2013 Control Panel.</span></span>

<div>

## <a name="to-delete-client-version-policy-rules-with-lync-server-control-panel"></a><span data-ttu-id="10934-107">使用 Lync Server 控制台刪除用戶端版本原則規則</span><span class="sxs-lookup"><span data-stu-id="10934-107">To delete client version policy rules with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="10934-108">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="10934-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="10934-109">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="10934-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="10934-110">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="10934-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="10934-111">在左導覽列中，按一下 [ **用戶端**]，然後按一下 [ **用戶端版本原則** ] 導覽按鈕。</span><span class="sxs-lookup"><span data-stu-id="10934-111">In the left navigation bar, click **Clients**, and then click the **Client Version Policy** navigation button.</span></span>

4.  <span data-ttu-id="10934-112">在 [ **用戶端版本原則** ] 頁面上，按兩下您要刪除之規則的用戶端版本原則。</span><span class="sxs-lookup"><span data-stu-id="10934-112">On the **Client Version Policy** page, double-click the client version policy for the rule you want to delete.</span></span>

5.  <span data-ttu-id="10934-113">規則會出現在 [ **編輯用戶端版本原則** ] 頁面上。</span><span class="sxs-lookup"><span data-stu-id="10934-113">The rules appear on the **Edit Client Version Policy** page.</span></span> <span data-ttu-id="10934-114">若要刪除規則，請選取規則，然後按一下 [ **移除**]。</span><span class="sxs-lookup"><span data-stu-id="10934-114">To delete a rule, select the rule, and then click **Remove**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

