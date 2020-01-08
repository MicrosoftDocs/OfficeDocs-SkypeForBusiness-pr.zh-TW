---
title: Lync Server 2013：安裝 Lync 會議室系統管理網頁入口網站
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing the Lync Room System Administrative Web Portal
ms:assetid: dd19e368-c338-4e21-a40d-6439d46a9748
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436326(v=OCS.15)
ms:contentKeyID: 56737622
ms.date: 04/09/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1c69231c6f07d2e57c0fe8be31d18ed6da109fc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974973"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a><span data-ttu-id="b759c-102">在 Lync Server 2013 中安裝 Lync 會議室系統管理網頁入口網站</span><span class="sxs-lookup"><span data-stu-id="b759c-102">Installing the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b759c-103">_**主題上次修改日期：** 2015-04-09_</span><span class="sxs-lookup"><span data-stu-id="b759c-103">_**Topic Last Modified:** 2015-04-09_</span></span>

<span data-ttu-id="b759c-104">您可以從 Microsoft 下載中心下載 Microsoft Lync 會議室系統管理網頁入口網站[http://go.microsoft.com/fwlink/p/?LinkId=324044](http://go.microsoft.com/fwlink/p/?linkid=324044)。</span><span class="sxs-lookup"><span data-stu-id="b759c-104">You can download the Microsoft Lync Room System Administrative Web Portal from the Microsoft Download Center at [http://go.microsoft.com/fwlink/p/?LinkId=324044](http://go.microsoft.com/fwlink/p/?linkid=324044).</span></span>

<span data-ttu-id="b759c-105">若要安裝 Lync 會議室系統管理網頁入口網站，請使用下列步驟。</span><span class="sxs-lookup"><span data-stu-id="b759c-105">To install the Lync Room System Administrative Web Portal, use the following steps.</span></span>

1.  <span data-ttu-id="b759c-106">在 Lync Server 管理命令介面中執行下列 Cmdlet，以設定受信任的應用程式埠：</span><span class="sxs-lookup"><span data-stu-id="b759c-106">Configure the Trusted Application Port by running the following cmdlet in Lync Server Management Shell:</span></span>
    
        Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457

2.  <span data-ttu-id="b759c-107">若要安裝會議室入口網站，請下載**LyncRoomAdminPortal** ，然後以系統管理員身分執行。</span><span class="sxs-lookup"><span data-stu-id="b759c-107">To install the Meeting Room Portal, download **LyncRoomAdminPortal.exe** and then run it as an administrator.</span></span>

3.  <span data-ttu-id="b759c-108">從下列位置開啟 Web.config 檔案：</span><span class="sxs-lookup"><span data-stu-id="b759c-108">Open the Web.config file from the following location:</span></span>
    
    <span data-ttu-id="b759c-109">% Program Files%\\Microsoft Lync Server 2013\\網頁元件\\會議室入口網站\\Int\\處理常式</span><span class="sxs-lookup"><span data-stu-id="b759c-109">%Program Files%\\Microsoft Lync Server 2013\\Web Components\\Meeting Room Portal\\Int\\Handler</span></span>\\

4.  <span data-ttu-id="b759c-110">在 web.config 檔案中，將 PortalUserName 變更為在步驟2中建立的使用者名稱，在「設定 Lync 聊天室系統管理入口網站的先決條件」區段（步驟中的建議名稱是 LRSApp）中。</span><span class="sxs-lookup"><span data-stu-id="b759c-110">In the Web.Config file, change the PortalUserName to the username created in Step 2 under the section “Configuring Prerequisites for Lync Room System Admin Portal” (the recommended name in the step is LRSApp):</span></span>
    
        <add key="PortalUserName" value="sip:LRSApp@domain.com" />

5.  <span data-ttu-id="b759c-111">因為 LRS 管理入口網站是受信任的應用程式，因此您不需要在入口網站設定中提供密碼。</span><span class="sxs-lookup"><span data-stu-id="b759c-111">Because the LRS Admin Portal is a trusted application, you do not need to provide the password in the portal configuration.</span></span> <span data-ttu-id="b759c-112">如果此使用者使用的註冊機構並非是本機註冊機構，您必須在 Web.config 檔案中加入下列一行，以指定其註冊機構：</span><span class="sxs-lookup"><span data-stu-id="b759c-112">If this user is using a different registrar than local registrar, you need to specify the registrar for it by adding the following line in the Web.Config file:</span></span>
    
        <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />

6.  <span data-ttu-id="b759c-113">如果使用的埠不是5061，請在 web.config 檔案中新增下列行：</span><span class="sxs-lookup"><span data-stu-id="b759c-113">If the port used is other than 5061, add the following line in the Web.Config file:</span></span>
    
        <add key="PortalUserRegistrarPort" value="5061" />

<div>

## <a name="verifying-installation-of-the-lync-room-system-administrative-web-portal"></a><span data-ttu-id="b759c-114">驗證 Lync 會議室系統管理網頁入口網站的安裝</span><span class="sxs-lookup"><span data-stu-id="b759c-114">Verifying Installation of the Lync Room System Administrative Web Portal</span></span>

<span data-ttu-id="b759c-115">若要確認 Lync 會議室系統管理網頁入口網站的安裝，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="b759c-115">To verify installation of the Lync Room System Administrative Web Portal, do the following:</span></span>


1.  <span data-ttu-id="b759c-116">在前端伺服器上，流覽至下列 URL：</span><span class="sxs-lookup"><span data-stu-id="b759c-116">On a Front End server, browse to the following URL:</span></span>
    
    <span data-ttu-id="b759c-117">HTTPs://\<fe-伺服器\>/lrs</span><span class="sxs-lookup"><span data-stu-id="b759c-117">https://\<fe-server\>/lrs</span></span>
    
    <span data-ttu-id="b759c-118">您不應該看到任何錯誤，如下圖所示：</span><span class="sxs-lookup"><span data-stu-id="b759c-118">You should not see any errors, as shown in the following image:</span></span>
    
    <span data-ttu-id="b759c-119">![Lync 會議室系統管理入口網站登入螢幕](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Lync 會議室系統管理入口網站登入畫面")</span><span class="sxs-lookup"><span data-stu-id="b759c-119">![Lync Room System Admin Portal Sign In screen](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Lync Room System Admin Portal Sign In screen")</span></span>

2.  <span data-ttu-id="b759c-120">如果您沒有看到任何錯誤，請嘗試從拓撲中的任何其他電腦存取下列 URL：</span><span class="sxs-lookup"><span data-stu-id="b759c-120">If you do not see any errors, try accessing the following URL from any other computer in the topology:</span></span>
    
    <span data-ttu-id="b759c-121">HTTPs://\<fe-伺服器\>/lrs</span><span class="sxs-lookup"><span data-stu-id="b759c-121">https://\<fe-server\>/lrs</span></span>
    
    <span data-ttu-id="b759c-122">若要存取頁面，您將需要新增 DNS 記錄，如「自動用戶端登入所需的 DNS 記錄」中所述[http://go.microsoft.com/fwlink/p/?LinkId=318056](http://go.microsoft.com/fwlink/p/?linkid=318056)。</span><span class="sxs-lookup"><span data-stu-id="b759c-122">To access the page, you will need to add the DNS records as described in “Required DNS Records for Automatic Client Sign-In” at [http://go.microsoft.com/fwlink/p/?LinkId=318056](http://go.microsoft.com/fwlink/p/?linkid=318056).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

