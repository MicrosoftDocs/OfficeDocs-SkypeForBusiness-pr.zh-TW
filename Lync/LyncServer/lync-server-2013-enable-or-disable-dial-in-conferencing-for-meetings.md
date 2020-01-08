---
title: Lync Server 2013：啟用或停用會議的電話撥入式會議
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable or disable dial-in conferencing for meetings
ms:assetid: 418dcf2d-c8d6-4b2c-b1ab-8723c7ef53e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688036(v=OCS.15)
ms:contentKeyID: 49733627
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b5df22a87208238c828b20e485a2ec416fcb3065
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976419"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-dial-in-conferencing-for-meetings-in-lync-server-2013"></a><span data-ttu-id="22486-102">在 Lync Server 2013 的會議中啟用或停用電話撥入式會議</span><span class="sxs-lookup"><span data-stu-id="22486-102">Enable or disable dial-in conferencing for meetings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="22486-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="22486-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="22486-104">下列程式說明如何允許使用者使用電話撥入來加入會議。</span><span class="sxs-lookup"><span data-stu-id="22486-104">The following procedure describes how to allow user to join a meeting using dial-in.</span></span>

<div>

## <a name="to-enable-or-disable-dial-in-conferencing"></a><span data-ttu-id="22486-105">啟用或停用電話撥入式會議</span><span class="sxs-lookup"><span data-stu-id="22486-105">To enable or disable dial-in conferencing</span></span>

1.  <span data-ttu-id="22486-106">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="22486-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="22486-107">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="22486-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="22486-108">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="22486-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="22486-109">在左側導覽列中，按一下 [**會議**]，然後按一下 [**會議原則**]。</span><span class="sxs-lookup"><span data-stu-id="22486-109">In the left navigation bar, click **Conferencing** and then click **Conferencing Policy**.</span></span>

4.  <span data-ttu-id="22486-110">在會議原則清單中，選取您要啟用電話撥入式會議的原則，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="22486-110">In the list of conferencing policies, select the policy for which you want to enable dial-in conferencing, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="22486-111">若要允許使用者透過撥入方式加入會議，請核取 [**啟用 PSTN 電話撥入式會議**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="22486-111">To allow users to join meeting by dialing in, check the **Enable PSTN dial-in conferencing** check box.</span></span> <span data-ttu-id="22486-112">根據預設，使用者可以使用公開交換電話網絡（PSTN）撥入會議。</span><span class="sxs-lookup"><span data-stu-id="22486-112">By default, users can dial in to meetings by using the public switched telephone network (PSTN).</span></span>

6.  <span data-ttu-id="22486-113">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="22486-113">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

