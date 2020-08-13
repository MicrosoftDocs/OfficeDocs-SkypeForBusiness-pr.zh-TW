---
title: Lync Server 2013：啟用或停用電話撥入式會議
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable dial-in conferencing for meetings
ms:assetid: 418dcf2d-c8d6-4b2c-b1ab-8723c7ef53e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688036(v=OCS.15)
ms:contentKeyID: 49733627
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b995ef14ad1b405b59eba8d54646989c9f63f43
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204829"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-dial-in-conferencing-for-meetings-in-lync-server-2013"></a><span data-ttu-id="d916d-102">在 Lync Server 2013 中啟用或停用電話撥入式會議</span><span class="sxs-lookup"><span data-stu-id="d916d-102">Enable or disable dial-in conferencing for meetings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d916d-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="d916d-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="d916d-104">下列程序描述如何使用撥入功能允許使用者加入會議。</span><span class="sxs-lookup"><span data-stu-id="d916d-104">The following procedure describes how to allow user to join a meeting using dial-in.</span></span>

<div>

## <a name="to-enable-or-disable-dial-in-conferencing"></a><span data-ttu-id="d916d-105">啟用或停用電話撥入式會議</span><span class="sxs-lookup"><span data-stu-id="d916d-105">To enable or disable dial-in conferencing</span></span>

1.  <span data-ttu-id="d916d-106">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="d916d-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d916d-107">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="d916d-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d916d-108">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="d916d-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d916d-109">在左導覽列中，按一下 **[會議]**，再按一下 **[會議原則]**。</span><span class="sxs-lookup"><span data-stu-id="d916d-109">In the left navigation bar, click **Conferencing** and then click **Conferencing Policy**.</span></span>

4.  <span data-ttu-id="d916d-110">在會議原則清單中，選取要啟用電話撥入式會議的原則，然後按一下 **[編輯]**，再按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="d916d-110">In the list of conferencing policies, select the policy for which you want to enable dial-in conferencing, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="d916d-p102">若要允許使用者藉由撥入電話來加入會議，請勾選 **[啟用 PSTN 電話撥入式會議]** 核取方塊。根據預設，使用者可以使用公用交換電話網路 (PSTN) 來撥入會議。</span><span class="sxs-lookup"><span data-stu-id="d916d-p102">To allow users to join meeting by dialing in, check the **Enable PSTN dial-in conferencing** check box. By default, users can dial in to meetings by using the public switched telephone network (PSTN).</span></span>

6.  <span data-ttu-id="d916d-113">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="d916d-113">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

