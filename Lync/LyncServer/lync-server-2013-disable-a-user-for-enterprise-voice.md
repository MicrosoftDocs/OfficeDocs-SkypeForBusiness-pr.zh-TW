---
title: Lync Server 2013：停用企業語音的使用者
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disable a user for Enterprise Voice
ms:assetid: 462002d8-21df-4d77-bf7f-4d059d6a4bb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688043(v=OCS.15)
ms:contentKeyID: 49733635
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aaa5058d820fc399d7f6b915407a62fc1031fa99
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529040"
---
# <a name="disable-a-user-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="81117-102">停用 Lync Server 2013 的 Enterprise Voice 使用者</span><span class="sxs-lookup"><span data-stu-id="81117-102">Disable a user for Enterprise Voice in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81117-103">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="81117-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="81117-104">使用下列程式可停用 Lync Server 2013 啟用之使用者帳戶的 Enterprise Voice。</span><span class="sxs-lookup"><span data-stu-id="81117-104">Use the following procedure to disable Enterprise Voice for a user account that is enabled for Lync Server 2013.</span></span>

<div>

## <a name="to-disable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="81117-105">停用 Enterprise Voice 的使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="81117-105">To disable a user account for Enterprise Voice</span></span>

1.  <span data-ttu-id="81117-106">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="81117-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="81117-107">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="81117-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="81117-108">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="81117-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="81117-109">在左導覽列中，按一下 **[使用者]**。</span><span class="sxs-lookup"><span data-stu-id="81117-109">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="81117-110">在 [ **搜尋使用者** ] 方塊中，輸入全部或部分的顯示名稱、名字、姓氏、安全性帳戶管理員 (SAM) 帳戶名稱、SIP 位址或線路統一資源識別項 (URI) 的使用者帳戶，然後按一下 [ **尋找**]。</span><span class="sxs-lookup"><span data-stu-id="81117-110">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="81117-111">在表格中，按一下您要為 Enterprise Voice 啟用的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="81117-111">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>

6.  <span data-ttu-id="81117-112">在 **[編輯]** 功能表上，按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="81117-112">On the **Edit** menu, click **Show details**.</span></span>

7.  <span data-ttu-id="81117-113">在 [ **編輯 Lync Server 使用者** ] 頁面的 [ **電話**語音] 下，按一下 [ **Enterprise Voice**以外的任何選項]。</span><span class="sxs-lookup"><span data-stu-id="81117-113">On the **Edit Lync Server User** page, under **Telephony**, click any option except **Enterprise Voice**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="81117-114">若要使用 Lync 限制使用者進行音訊或視頻通話，請在 [ <STRONG>電話語音</STRONG>] 下，按一下 [ <STRONG>音訊/視頻已停用</STRONG>]。</span><span class="sxs-lookup"><span data-stu-id="81117-114">To restrict a user from making audio or video calls by using Lync, under <STRONG>Telephony</STRONG>, click <STRONG>Audio/video disabled</STRONG>.</span></span>

    
    </div>

8.  <span data-ttu-id="81117-115">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="81117-115">Click **Commit**.</span></span>

<span data-ttu-id="81117-116">使用者現在無法使用 Enterprise Voice 功能。</span><span class="sxs-lookup"><span data-stu-id="81117-116">The user is now unable to use the Enterprise Voice feature.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="81117-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="81117-117">See Also</span></span>


[<span data-ttu-id="81117-118">在 Lync Server 2013 中啟用使用者的 Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="81117-118">Enable users for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-enable-users-for-enterprise-voice.md)  


[<span data-ttu-id="81117-119">在 Lync Server 2013 中管理使用者的企業語音</span><span class="sxs-lookup"><span data-stu-id="81117-119">Managing Enterprise Voice for users in Lync Server 2013</span></span>](lync-server-2013-managing-enterprise-voice-for-users.md)  
[<span data-ttu-id="81117-120">Lync Server 2013 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="81117-120">Lync Server 2013 Management Shell</span></span>](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

