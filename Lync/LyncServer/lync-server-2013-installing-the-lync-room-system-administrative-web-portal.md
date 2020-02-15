---
title: Lync Server 2013： 安裝 Lync 會議室系統管理的入口網站
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Lync Room System Administrative Web Portal
ms:assetid: dd19e368-c338-4e21-a40d-6439d46a9748
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436326(v=OCS.15)
ms:contentKeyID: 56737622
ms.date: 04/09/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6af0f52b940e9bcfb78048ef3a2c60f09d265073
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045235"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a><span data-ttu-id="f1e3e-102">安裝 Lync Server 2013 中的 Lync 會議室系統管理的入口網站</span><span class="sxs-lookup"><span data-stu-id="f1e3e-102">Installing the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1e3e-103">_**主題上次修改日期：** 2015年-04-09_</span><span class="sxs-lookup"><span data-stu-id="f1e3e-103">_**Topic Last Modified:** 2015-04-09_</span></span>

<span data-ttu-id="f1e3e-104">您可以從 Microsoft 下載中心下載 Microsoft Lync 會議室系統管理入口網站[http://go.microsoft.com/fwlink/p/?LinkId=324044](http://go.microsoft.com/fwlink/p/?linkid=324044)。</span><span class="sxs-lookup"><span data-stu-id="f1e3e-104">You can download the Microsoft Lync Room System Administrative Web Portal from the Microsoft Download Center at [http://go.microsoft.com/fwlink/p/?LinkId=324044](http://go.microsoft.com/fwlink/p/?linkid=324044).</span></span>

<span data-ttu-id="f1e3e-105">若要安裝 Lync 會議室系統管理入口網站，請使用下列步驟。</span><span class="sxs-lookup"><span data-stu-id="f1e3e-105">To install the Lync Room System Administrative Web Portal, use the following steps.</span></span>

1.  <span data-ttu-id="f1e3e-106">在 Lync Server 管理命令介面中執行下列 cmdlet 來設定信任的應用程式連接埠：</span><span class="sxs-lookup"><span data-stu-id="f1e3e-106">Configure the Trusted Application Port by running the following cmdlet in Lync Server Management Shell:</span></span>
    
        Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457

2.  <span data-ttu-id="f1e3e-107">若要安裝會議會議室入口網站，請下載**LyncRoomAdminPortal.exe**並再執行身為系統管理員。</span><span class="sxs-lookup"><span data-stu-id="f1e3e-107">To install the Meeting Room Portal, download **LyncRoomAdminPortal.exe** and then run it as an administrator.</span></span>

3.  <span data-ttu-id="f1e3e-108">開啟 Web.config 檔案，從下列位置：</span><span class="sxs-lookup"><span data-stu-id="f1e3e-108">Open the Web.config file from the following location:</span></span>
    
    <span data-ttu-id="f1e3e-109">%程式檔案 %\\Microsoft Lync Server 2013\\Web 元件\\會議會議室入口網站\\Int\\處理常式</span><span class="sxs-lookup"><span data-stu-id="f1e3e-109">%Program Files%\\Microsoft Lync Server 2013\\Web Components\\Meeting Room Portal\\Int\\Handler</span></span>\\

4.  <span data-ttu-id="f1e3e-110">在 Web.Config 檔案中，變更 PortalUserName 為在步驟 2 中建立的 「 設定必要條件的 Lync 會議室系統管理員入口網站 」 （中步驟的建議的名稱是 LRSApp）] 區段下的使用者名稱：</span><span class="sxs-lookup"><span data-stu-id="f1e3e-110">In the Web.Config file, change the PortalUserName to the username created in Step 2 under the section “Configuring Prerequisites for Lync Room System Admin Portal” (the recommended name in the step is LRSApp):</span></span>
    
        <add key="PortalUserName" value="sip:LRSApp@domain.com" />

5.  <span data-ttu-id="f1e3e-111">因為 LRS 系統管理入口網站中的受信任的應用程式，您不需要提供入口網站設定中的密碼。</span><span class="sxs-lookup"><span data-stu-id="f1e3e-111">Because the LRS Admin Portal is a trusted application, you do not need to provide the password in the portal configuration.</span></span> <span data-ttu-id="f1e3e-112">如果此使用者使用本機登錄器比其他註冊機構，您需要指定它的登錄器的 Web.Config 檔案中加入下行：</span><span class="sxs-lookup"><span data-stu-id="f1e3e-112">If this user is using a different registrar than local registrar, you need to specify the registrar for it by adding the following line in the Web.Config file:</span></span>
    
        <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />

6.  <span data-ttu-id="f1e3e-113">如果使用的連接埠 5061 以外，請在 Web.Config 檔案中加入下列一行：</span><span class="sxs-lookup"><span data-stu-id="f1e3e-113">If the port used is other than 5061, add the following line in the Web.Config file:</span></span>
    
        <add key="PortalUserRegistrarPort" value="5061" />

<div>

## <a name="verifying-installation-of-the-lync-room-system-administrative-web-portal"></a><span data-ttu-id="f1e3e-114">確認 Lync 會議室系統管理 Web 入口網站的安裝</span><span class="sxs-lookup"><span data-stu-id="f1e3e-114">Verifying Installation of the Lync Room System Administrative Web Portal</span></span>

<span data-ttu-id="f1e3e-115">若要確認安裝 Lync 會議室系統管理入口網站，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="f1e3e-115">To verify installation of the Lync Room System Administrative Web Portal, do the following:</span></span>


1.  <span data-ttu-id="f1e3e-116">在前端伺服器上，瀏覽至下列 URL:</span><span class="sxs-lookup"><span data-stu-id="f1e3e-116">On a Front End server, browse to the following URL:</span></span>
    
    <span data-ttu-id="f1e3e-117">https://\<fe-server\>/lrs</span><span class="sxs-lookup"><span data-stu-id="f1e3e-117">https://\<fe-server\>/lrs</span></span>
    
    <span data-ttu-id="f1e3e-118">下圖所示，應該不會看到任何錯誤：</span><span class="sxs-lookup"><span data-stu-id="f1e3e-118">You should not see any errors, as shown in the following image:</span></span>
    
    <span data-ttu-id="f1e3e-119">![Lync 會議室系統管理員入口網站登入畫面](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Lync 會議室系統管理員入口網站登入畫面")</span><span class="sxs-lookup"><span data-stu-id="f1e3e-119">![Lync Room System Admin Portal Sign In screen](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Lync Room System Admin Portal Sign In screen")</span></span>

2.  <span data-ttu-id="f1e3e-120">如果看不到任何錯誤，請嘗試從拓撲中的任何其他電腦存取下列 URL:</span><span class="sxs-lookup"><span data-stu-id="f1e3e-120">If you do not see any errors, try accessing the following URL from any other computer in the topology:</span></span>
    
    <span data-ttu-id="f1e3e-121">https://\<fe-server\>/lrs</span><span class="sxs-lookup"><span data-stu-id="f1e3e-121">https://\<fe-server\>/lrs</span></span>
    
    <span data-ttu-id="f1e3e-122">若要存取 [] 頁面上，您必須新增 DNS 記錄所述的 「 需要 DNS 記錄的自動用戶端登入 」 在[http://go.microsoft.com/fwlink/p/?LinkId=318056](http://go.microsoft.com/fwlink/p/?linkid=318056)。</span><span class="sxs-lookup"><span data-stu-id="f1e3e-122">To access the page, you will need to add the DNS records as described in “Required DNS Records for Automatic Client Sign-In” at [http://go.microsoft.com/fwlink/p/?LinkId=318056](http://go.microsoft.com/fwlink/p/?linkid=318056).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

