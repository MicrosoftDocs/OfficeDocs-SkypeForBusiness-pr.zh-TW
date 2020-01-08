---
title: Lync Server 2013：設定使用者帳戶設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure user account settings
ms:assetid: b7c74ecc-b924-4efc-8a56-3a5f94a9ef13
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412896(v=OCS.15)
ms:contentKeyID: 48185200
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b4d06405d2f80aef5decb69d564ae399401d4328
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974629"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-user-account-settings-in-lync-server-2013"></a><span data-ttu-id="82dc9-102">在 Lync Server 2013 中設定使用者帳戶設定</span><span class="sxs-lookup"><span data-stu-id="82dc9-102">Configure user account settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82dc9-103">_**主題上次修改日期：** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="82dc9-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="82dc9-104">[撥入使用者] 輸入他們的電話號碼或分機，以及將會議加入為經過驗證的使用者的 PIN。</span><span class="sxs-lookup"><span data-stu-id="82dc9-104">Dial-in users enter their phone number or extension and a PIN to join conferences as authenticated users.</span></span> <span data-ttu-id="82dc9-105">需要在 Lync Server 使用者帳戶上指定的電話**線路 URI** ，才能進行驗證。</span><span class="sxs-lookup"><span data-stu-id="82dc9-105">The telephony **Line URI** specified on Lync Server user accounts is required for authentication.</span></span>

<span data-ttu-id="82dc9-106">本主題中的程式說明如何為單一使用者帳戶指派**行 URI** 。</span><span class="sxs-lookup"><span data-stu-id="82dc9-106">The procedure in this topic describes how to assign a **Line URI** for a single user account.</span></span> <span data-ttu-id="82dc9-107">如果您需要為多個使用者帳戶指派**行 URI** ，您可以建立使用**move-csuser** Cmdlet 的腳本。</span><span class="sxs-lookup"><span data-stu-id="82dc9-107">If you need to assign a **Line URI** for multiple user accounts, you can create a script that uses the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="82dc9-108">如需使用範例腳本將**行 URI**指派給多個使用者帳戶的詳細資料，請參閱「指派行 Uri 給多位[http://go.microsoft.com/fwlink/p/?linkId=196945](http://go.microsoft.com/fwlink/p/?linkid=196945)使用者」。</span><span class="sxs-lookup"><span data-stu-id="82dc9-108">For details about using a sample script to assign **Line URI** to multiple user accounts, see "Assign Line URIs to Multiple Users" at [http://go.microsoft.com/fwlink/p/?linkId=196945](http://go.microsoft.com/fwlink/p/?linkid=196945).</span></span>

<div>

## <a name="to-configure-user-account-settings"></a><span data-ttu-id="82dc9-109">設定使用者帳戶設定</span><span class="sxs-lookup"><span data-stu-id="82dc9-109">To configure user account settings</span></span>

1.  <span data-ttu-id="82dc9-110">以 RTCUniversalServerAdmins 群組的成員或**Cs-UserAdministrator**或**CsAdministrator**角色的成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="82dc9-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-UserAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="82dc9-111">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="82dc9-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="82dc9-112">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="82dc9-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="82dc9-113">在左側導覽列中，按一下 [**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="82dc9-113">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="82dc9-114">在 [搜尋] 欄位中，輸入您要為電話撥入式會議設定的使用者名稱，或按一下 [**新增篩選**] 以指定搜尋欄位，然後按一下 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="82dc9-114">In the search field, type the name of the user you want to configure for dial-in conferencing or click **Add filter** to specify search fields, and then click **Find**.</span></span>

5.  <span data-ttu-id="82dc9-115">按兩下使用者名稱以開啟 [**編輯 Lync Server 使用者**] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="82dc9-115">Double-click the user name to open the **Edit Lync Server User** dialog box.</span></span>

6.  <span data-ttu-id="82dc9-116">在 [**電話**] 底下的 [**行 URI** ] 欄位中，輸入唯一的、標準化的電話號碼（例如電話： + 14255550200）。</span><span class="sxs-lookup"><span data-stu-id="82dc9-116">Under **Telephony**, in the **Line URI** field, type a unique, normalized phone number (for example, tel:+14255550200).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="82dc9-117">只有將<STRONG>電話</STRONG>設定為 [<STRONG>僅電腦至電腦</STRONG>]、[<STRONG>企業語音</STRONG>]、[<STRONG>遠端通話控制</STRONG>] 或 [<STRONG>遠端通話控制</STRONG>] 時，才能指定 [<STRONG>行 URI</STRONG> ]。</span><span class="sxs-lookup"><span data-stu-id="82dc9-117">You can specify <STRONG>Line URI</STRONG> only if <STRONG>Telephony</STRONG> is set to <STRONG>PC-to-PC only</STRONG>, <STRONG>Enterprise Voice</STRONG>, <STRONG>Remote call control</STRONG> or <STRONG>Remote call control only</STRONG>.</span></span>

    
    </div>

7.  <span data-ttu-id="82dc9-118">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="82dc9-118">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

