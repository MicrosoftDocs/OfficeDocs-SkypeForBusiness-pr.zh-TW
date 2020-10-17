---
title: Lync Server 2013：測試 Director
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test the Director
ms:assetid: 9627a7e2-28cc-429c-b79b-7c7a27573bb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398767(v=OCS.15)
ms:contentKeyID: 48184856
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae7f2945cd3a21ea93969e098110fadec710cb98
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519090"
---
# <a name="test-the-director-in-lync-server-2013"></a><span data-ttu-id="d6000-102">在 Lync Server 2013 中測試 Director</span><span class="sxs-lookup"><span data-stu-id="d6000-102">Test the Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d6000-103">_**主題上次修改日期：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="d6000-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="d6000-104">在此階段中，您已設定 Director 或 Director 集區，但是您的網域名稱系統 (DNS) SRV 專案仍指向使用集區或 Standard Edition server 來登入的用戶端。</span><span class="sxs-lookup"><span data-stu-id="d6000-104">At this stage, you have a Director or Director pool configured, but your Domain Name System (DNS) SRV entries still point clients to log on by using a pool or Standard Edition server.</span></span> <span data-ttu-id="d6000-105">在使用 Director 變更 DNS 記錄以使 Lync 2013 用戶端自動登入之前，請透過手動將用戶端指向 Director 來測試用戶端。</span><span class="sxs-lookup"><span data-stu-id="d6000-105">Before changing the DNS record to make Lync 2013 clients log on automatically by using the Director, test a client by manually pointing it to the Director.</span></span>

<div>

## <a name="to-test-the-deployment"></a><span data-ttu-id="d6000-106">測試部署</span><span class="sxs-lookup"><span data-stu-id="d6000-106">To test the deployment</span></span>

1.  <span data-ttu-id="d6000-107">使用屬於 **CSAdministrator** 群組的網域帳戶，登入已安裝 Lync Server 控制台的電腦。</span><span class="sxs-lookup"><span data-stu-id="d6000-107">Log on to the computer on which you have the Lync Server Control Panel installed with a domain account that is part of the **CSAdministrator** group.</span></span>

2.  <span data-ttu-id="d6000-108">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="d6000-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d6000-109">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="d6000-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d6000-110">在功能窗格中，按一下 [ **拓撲**]，然後在 [ **狀態** ] 欄中，確認有箭號 (的綠色伺服器，也就是您 director 或 director 集區的 ![綠色箭頭) 伺服器圖示](images/Gg398767.2263cdb7-7e60-457a-a528-a3a082bd051b(OCS.15).jpg "具有綠色箭頭的伺服器圖示") 。</span><span class="sxs-lookup"><span data-stu-id="d6000-110">In the navigation pane, click **Topology**, and in the **Status** column confirm that there is a green server with an arrow (that is, ![Server icon with green arrow](images/Gg398767.2263cdb7-7e60-457a-a528-a3a082bd051b(OCS.15).jpg "Server icon with green arrow")) for your Director or Director pool.</span></span>

4.  <span data-ttu-id="d6000-111">連接兩部已安裝 Lync Server 2013 用戶端的用戶端電腦，並以 Lync Server 2013 各自啟用的不同使用者帳戶登入每一部電腦。</span><span class="sxs-lookup"><span data-stu-id="d6000-111">Connect two client computers that have the Lync Server 2013 client installed and log on with a different user account enabled for Lync Server 2013 to each computer.</span></span>

5.  <span data-ttu-id="d6000-112">在其中一部用戶端電腦上，按一下 [ **選項** ] 功能表，選取 [ **個人** 設定] 群組，按一下 [ **高級**]，按一下 [ **手動**設定]，然後將 **內部伺服器名稱或 IP 位址** 設定為新 Director 或 Director 集區的 FQDN)  (FQDN。</span><span class="sxs-lookup"><span data-stu-id="d6000-112">On one of the client computers, click the **Options** menu, select the **Personal** settings group, click **Advanced**, click **Manual Configuration**, and then set the **Internal Server name or IP address** to the fully qualified domain name (FQDN) of the new Director or Director pool.</span></span>

6.  <span data-ttu-id="d6000-113">登入這兩個用戶端，並確認使用 Director 登入的用戶端能夠順利登入、查看其他使用者的目前狀態，以及他們是否可以 exchange 立即訊息。</span><span class="sxs-lookup"><span data-stu-id="d6000-113">Log on to both clients and verify that the client logging on by using the Director is able to log on successfully, see the presence status of the other user, and that they can exchange instant messages.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

