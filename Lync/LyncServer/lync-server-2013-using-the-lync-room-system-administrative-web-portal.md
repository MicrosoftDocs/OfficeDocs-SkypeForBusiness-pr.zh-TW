---
title: Lync Server 2013： 使用 Lync 會議室系統管理 Web 入口網站
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Lync Room System Administrative Web Portal
ms:assetid: c387b2a3-3e42-4642-af72-88126ed2820f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743660(v=OCS.15)
ms:contentKeyID: 62268951
ms.date: 11/13/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 759cae91575d3244d6860c6ec76fa664994d493e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138614"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a><span data-ttu-id="56f20-102">使用 Lync Server 2013 中的 Lync 會議室系統管理 Web 入口網站</span><span class="sxs-lookup"><span data-stu-id="56f20-102">Using the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="56f20-103">_**上次修改主題：** 2014年-11-10_</span><span class="sxs-lookup"><span data-stu-id="56f20-103">_**Topic Last Modified:** 2014-11-10_</span></span>

<span data-ttu-id="56f20-104">在伺服器上部署 LRS 之後，您可以藉由登入 LRS 管理入口網站從瀏覽器檢查所有 LRS 會議室的狀態。</span><span class="sxs-lookup"><span data-stu-id="56f20-104">After you deploy LRS on the server, you can check the status of all LRS rooms by signing into the LRS Administrative Web Portal from a browser.</span></span>

<div>

## <a name="sign-in"></a><span data-ttu-id="56f20-105">登入</span><span class="sxs-lookup"><span data-stu-id="56f20-105">Sign in</span></span>

1.  <span data-ttu-id="56f20-106">瀏覽至下列 URL:</span><span class="sxs-lookup"><span data-stu-id="56f20-106">Browse to the following URL:</span></span>
    
    <span data-ttu-id="56f20-107">https://\<fe-server\>/lrs</span><span class="sxs-lookup"><span data-stu-id="56f20-107">https://\<fe-server\>/lrs</span></span>

2.  <span data-ttu-id="56f20-108">輸入 LRSSupport 帳戶或已新增至 LRSSupportAdminGroup 的 [安全性] 群組帳戶的認證。</span><span class="sxs-lookup"><span data-stu-id="56f20-108">Enter the credentials for the LRSSupport account or an account that has been added to the LRSSupportAdminGroup security group.</span></span>

<span data-ttu-id="56f20-109">![Lync 會議室系統管理員入口網站登入畫面](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Lync 會議室系統管理員入口網站登入畫面")</span><span class="sxs-lookup"><span data-stu-id="56f20-109">![Lync Room System Admin Portal Sign In screen](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Lync Room System Admin Portal Sign In screen")</span></span>

</div>

<div>

## <a name="lrs-administrative-web-portal-summary-page"></a><span data-ttu-id="56f20-110">LRS 系統管理網站的入口網站摘要頁面</span><span class="sxs-lookup"><span data-stu-id="56f20-110">LRS Administrative Web Portal Summary Page</span></span>

<span data-ttu-id="56f20-111">[摘要] 頁面上提供所有伺服器上部署 LRS 會議室的下列的資訊：</span><span class="sxs-lookup"><span data-stu-id="56f20-111">The summary page provides the following information for all of the LRS rooms deployed on the server:</span></span>

  - <span data-ttu-id="56f20-112">**標記**   自訂會議室可讓系統管理員的名稱。</span><span class="sxs-lookup"><span data-stu-id="56f20-112">**Tag**   The custom name that the administrator gives to the room.</span></span> <span data-ttu-id="56f20-113">標籤可以設定入口網站中，會議室名稱上按一下。</span><span class="sxs-lookup"><span data-stu-id="56f20-113">The Tag can be set in the portal by clicking on the room name.</span></span>

  - <span data-ttu-id="56f20-114">**健康情況**   會議室，衍生自會議室，會顯示在 [聊天室設定] 頁面的 [健康情況] 區段下方的彙總的健康狀態的健康狀態。</span><span class="sxs-lookup"><span data-stu-id="56f20-114">**Health**   The health status of the room, which is derived from the Aggregate Health status of the room, which is shown under the Health section of the Room Settings page.</span></span>

  - <span data-ttu-id="56f20-115">**接下來會議**   的日期和時間排定的下一個會議。</span><span class="sxs-lookup"><span data-stu-id="56f20-115">**Next Meeting**   The date and time the next meeting is scheduled.</span></span>

  - <span data-ttu-id="56f20-116">**LRS 版本，製造商、 模型**   這些值都會在 LRS 預先設定好。</span><span class="sxs-lookup"><span data-stu-id="56f20-116">**LRS Version, Manufacturer, Model**   These values are preset in LRS.</span></span> <span data-ttu-id="56f20-117">根據製造商，這些欄位可能會留白。</span><span class="sxs-lookup"><span data-stu-id="56f20-117">Depending on the manufacturer, these fields might be left blank.</span></span>

  - <span data-ttu-id="56f20-118">**上次重新整理**   會顯示的上次在重新整理網頁。</span><span class="sxs-lookup"><span data-stu-id="56f20-118">**Last Refresh**   Displays the last time the webpage was refreshed.</span></span>

<span data-ttu-id="56f20-119">![Lync 會議室系統系統管理入口網站摘要檢視](images/Dn743660.f829ce90-dd95-4725-bd94-6870c5dcf046(OCS.15).png "Lync 會議室系統系統管理入口網站摘要檢視")</span><span class="sxs-lookup"><span data-stu-id="56f20-119">![Lync Room System Admin Portal Summary View](images/Dn743660.f829ce90-dd95-4725-bd94-6870c5dcf046(OCS.15).png "Lync Room System Admin Portal Summary View")</span></span>

</div>

<div>

## <a name="lrs-room-information"></a><span data-ttu-id="56f20-120">LRS 會議室的資訊</span><span class="sxs-lookup"><span data-stu-id="56f20-120">LRS Room Information</span></span>

<span data-ttu-id="56f20-121">入口網站的 [會議室資訊] 區段可讓您檢視和設定個別 LRS 聊天室。</span><span class="sxs-lookup"><span data-stu-id="56f20-121">The Room Info section of the portal allows you to view and configure individual LRS rooms.</span></span> <span data-ttu-id="56f20-122">它包含四個區段： 設定、 詳細資料、 疑難排解和健康情況。</span><span class="sxs-lookup"><span data-stu-id="56f20-122">It contains four sections: Settings, Details, Troubleshooting, and Health.</span></span>

<div>

## <a name="settings"></a><span data-ttu-id="56f20-123">設定</span><span class="sxs-lookup"><span data-stu-id="56f20-123">Settings</span></span>

<span data-ttu-id="56f20-124">在 [設定] 區段中，您可以設定密碼會議室標記，預設磁碟區層級的會議室。</span><span class="sxs-lookup"><span data-stu-id="56f20-124">In the Settings section, you can set the password, room tag, and default volume levels for the room.</span></span> <span data-ttu-id="56f20-125">如果您設定這些設定，所做的變更會複寫只有在您重新啟動 LRS 主控台之後。</span><span class="sxs-lookup"><span data-stu-id="56f20-125">If you configure these settings, the changes are replicated only after you restart the LRS console.</span></span> <span data-ttu-id="56f20-126">您只會看到 Lync 會議室系統所 15.12 和更新版本的版本的系統更新設定。</span><span class="sxs-lookup"><span data-stu-id="56f20-126">You will only see System Updates settings for Lync Room Systems that are version 15.12 and later.</span></span>

<span data-ttu-id="56f20-127">![Lync 會議室系統管理入口會議室設定](images/Dn743660.ab162e19-41ac-4991-9b2a-92575aa53eda(OCS.15).png "Lync 會議室系統管理入口會議室設定")</span><span class="sxs-lookup"><span data-stu-id="56f20-127">![Lync Room System Admin Portal Room Settings](images/Dn743660.ab162e19-41ac-4991-9b2a-92575aa53eda(OCS.15).png "Lync Room System Admin Portal Room Settings")</span></span>

</div>

<div>

## <a name="details"></a><span data-ttu-id="56f20-128">詳細資料</span><span class="sxs-lookup"><span data-stu-id="56f20-128">Details</span></span>

<span data-ttu-id="56f20-129">[詳細資料] 區段中提供 LRS 會議室的設定，包括唯讀摘要： 上次重新整理; 的時間下一個會議;上次更新、 維護和校正;預設的喇叭、 麥克風，以及響鈴設定;版本;SIP URI;畫面及詳細資料每一個畫面中; 的數目狀態和活動。</span><span class="sxs-lookup"><span data-stu-id="56f20-129">The Details section provides a read-only summary of the LRS room’s settings, including: the time of last refresh; next meeting; last updates, maintenance and calibration; default speaker, mic, and ringer settings; version; SIP URI; number of screens and details about each screen; status, and activity.</span></span>

<span data-ttu-id="56f20-130">![Lync 會議室系統系統管理入口網站詳細資料檢視](images/Dn743660.2958bbba-db74-4670-a920-87fdfb2fc22d(OCS.15).png "Lync 會議室系統系統管理入口網站詳細資料檢視")</span><span class="sxs-lookup"><span data-stu-id="56f20-130">![Lync Room System Admin Portal Detail View](images/Dn743660.2958bbba-db74-4670-a920-87fdfb2fc22d(OCS.15).png "Lync Room System Admin Portal Detail View")</span></span>

</div>

<div>

## <a name="troubleshooting"></a><span data-ttu-id="56f20-131">疑難排解</span><span class="sxs-lookup"><span data-stu-id="56f20-131">Troubleshooting</span></span>

<span data-ttu-id="56f20-132">[疑難排解] 區段可用來從遠端收集記錄，並將其儲存至指定的位置。</span><span class="sxs-lookup"><span data-stu-id="56f20-132">The Troubleshooting section can be used to remotely collect logs and save them to a specified location.</span></span> <span data-ttu-id="56f20-133">您也可以重新啟動 LRS 主控台 （LRS 使用者介面），或重新啟動整個系統。</span><span class="sxs-lookup"><span data-stu-id="56f20-133">You can also restart the LRS console (LRS user interface) or restart the entire system.</span></span> <span data-ttu-id="56f20-134">若要收集記錄，提供指定之格式的資料夾路徑，並請確定在資料夾的寫入權限指定給 LRS 電腦帳戶。</span><span class="sxs-lookup"><span data-stu-id="56f20-134">To collect logs, provide a folder path in the specified format and make sure that the folder has write permissions given to the LRS machine account.</span></span> <span data-ttu-id="56f20-135">記錄檔的大小過大時，可能需要 5 分鐘的時間來完成 [收集記錄檔。</span><span class="sxs-lookup"><span data-stu-id="56f20-135">If the log size is too big, it can take up to 5 minutes to finish collecting logs.</span></span> <span data-ttu-id="56f20-136">重新整理] 頁面上，會提供最新狀態。</span><span class="sxs-lookup"><span data-stu-id="56f20-136">Refreshing the page will give you the latest status.</span></span>

<span data-ttu-id="56f20-137">![Lync 會議室系統管理員入口網站的會議室記錄](images/Dn743660.749aee71-deaa-4ace-a146-fe2b349f0f42(OCS.15).png "Lync 會議室系統管理員入口網站的會議室記錄")</span><span class="sxs-lookup"><span data-stu-id="56f20-137">![Lync Room System Admin Portal Room Logging](images/Dn743660.749aee71-deaa-4ace-a146-fe2b349f0f42(OCS.15).png "Lync Room System Admin Portal Room Logging")</span></span>

</div>

<div>

## <a name="health"></a><span data-ttu-id="56f20-138">醫療保健</span><span class="sxs-lookup"><span data-stu-id="56f20-138">Health</span></span>

<span data-ttu-id="56f20-139">[健康情況] 區段中提供 Lync Server 連線、 音訊裝置、 視訊裝置、 恢復能力的狀態，與螢幕裝置健全狀況的視覺的指示。</span><span class="sxs-lookup"><span data-stu-id="56f20-139">The Health section gives a visual indication of the health of the Lync Server connection, audio device, video device, resiliency state, and screen device.</span></span>

<span data-ttu-id="56f20-140">![Lync 會議室系統管理入口會議室健康狀況](images/Dn743660.8cc644f8-8e3e-42d5-9079-045d8fe9daa7(OCS.15).png "Lync 會議室系統管理入口會議室健康狀況")</span><span class="sxs-lookup"><span data-stu-id="56f20-140">![Lync Room System Admin Portal Room Health](images/Dn743660.8cc644f8-8e3e-42d5-9079-045d8fe9daa7(OCS.15).png "Lync Room System Admin Portal Room Health")</span></span>

</div>

</div>

<div>

## <a name="additional-notes-about-the-administrative-web-portal"></a><span data-ttu-id="56f20-141">管理 Web 入口網站的其他備註</span><span class="sxs-lookup"><span data-stu-id="56f20-141">Additional Notes about the Administrative Web Portal</span></span>

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="56f20-142">只有在 LRS 系統重新啟動之後，會套用設定變更。</span><span class="sxs-lookup"><span data-stu-id="56f20-142">Setting changes are applied only after the LRS system is restarted.</span></span></P>
> <LI>
> <P><span data-ttu-id="56f20-143">如果 LRSApp 帳戶密碼到期，您將無法查看會議室的狀態。</span><span class="sxs-lookup"><span data-stu-id="56f20-143">If the LRSApp account password expires, you will not be able to see the status of the rooms.</span></span> <span data-ttu-id="56f20-144">設定 LRSAppuser 帳戶密碼，讓它永遠不會到期，或請務必更新密碼時，它會接近到期日。</span><span class="sxs-lookup"><span data-stu-id="56f20-144">Configure the LRSAppuser account password so that it never expires, or be sure to update the password when it’s near expiration.</span></span></P>
> <LI>
> <P><span data-ttu-id="56f20-145">內部部署只支援 LRS 管理 web 入口網站。</span><span class="sxs-lookup"><span data-stu-id="56f20-145">The LRS administrative web portal is supported for on-premises deployments only.</span></span></P></LI></UL>



</div>

</div>

<div>

## <a name="frequently-asked-questions"></a><span data-ttu-id="56f20-146">常見問題集</span><span class="sxs-lookup"><span data-stu-id="56f20-146">Frequently Asked Questions</span></span>

<div>

## <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a><span data-ttu-id="56f20-147">為什麼無法我登入系統管理 web 入口網站？</span><span class="sxs-lookup"><span data-stu-id="56f20-147">Why can’t I sign in to the administrative web portal?</span></span>

  - <span data-ttu-id="56f20-148">當您開啟https://localhost/lrs，您將能夠看到登入] 頁面上，但當您輸入您的認證，您無法登入。</span><span class="sxs-lookup"><span data-stu-id="56f20-148">When you open https://localhost/lrs, you will be able to see the sign in page, but when you type in your credentials, you cannot sign in.</span></span> <span data-ttu-id="56f20-149">在此情況下，您必須開啟https://FQDNofFEserver/lrs來登入系統管理 web 入口網站。</span><span class="sxs-lookup"><span data-stu-id="56f20-149">In this case, you must open https://FQDNofFEserver/lrs to sign in to the administrative web portal.</span></span>

  - <span data-ttu-id="56f20-150">如果您在此存取管理 web 入口網站的電腦在工作群組，將無法運作 」 http:// 」。</span><span class="sxs-lookup"><span data-stu-id="56f20-150">If the machine from which you are accessing the administrative web portal is in a workgroup, "http://" will not work.</span></span> <span data-ttu-id="56f20-151">請改用"https"。</span><span class="sxs-lookup"><span data-stu-id="56f20-151">Use "https" instead.</span></span>

</div>

<div>

## <a name="why-cant-i-see-lrs-in-the-administrative-web-portal"></a><span data-ttu-id="56f20-152">為什麼在管理 web 入口網站中看不到 LRS？</span><span class="sxs-lookup"><span data-stu-id="56f20-152">Why can’t I see LRS in the administrative web portal?</span></span>

  - <span data-ttu-id="56f20-153">請確定您有 LRS 帳戶，您在部署中的，而且它們會建立根據 LRS 管理入口網站部署建議事項等。</span><span class="sxs-lookup"><span data-stu-id="56f20-153">Make sure you have LRS accounts in your deployment and that they are created according to the LRS Administrative Web Portal deployment recommendations.</span></span> <span data-ttu-id="56f20-154">請確定 LRS 帳戶佈建使用 Enable-csmeetingroom，未啟用 Get-csuser，Lync server 上。</span><span class="sxs-lookup"><span data-stu-id="56f20-154">Make sure the LRS accounts are provisioned using Enable-CsMeetingRoom, not Enable-CsUser, on the Lync server.</span></span>

  - <span data-ttu-id="56f20-155">如果您已經建立 LRS 帳戶，而無法看到管理 web 入口網站中的帳戶，收集伺服器記錄檔與**MeetingPortal**元件選取，請使用 Lync Server 記錄工具，並再將它們傳送到您 LRS 支援連絡人。</span><span class="sxs-lookup"><span data-stu-id="56f20-155">If you have created LRS accounts and cannot see the accounts in administrative web portal, collect the server logs by using the Lync Server Logging tool with the **MeetingPortal** component selected, and then send them to your LRS support contact.</span></span>

</div>

<div>

## <a name="why-cant-i-see-the-status-of-lrs-in-the-administrative-web-portal"></a><span data-ttu-id="56f20-156">為什麼無法看到 LRS 管理 web 入口網站中的狀態？</span><span class="sxs-lookup"><span data-stu-id="56f20-156">Why can’t I see the status of LRS in the administrative web portal?</span></span>

  - <span data-ttu-id="56f20-157">請確定 LRSApp 使用者帳戶是已啟用 SIP 的。</span><span class="sxs-lookup"><span data-stu-id="56f20-157">Make sure that the LRSApp user account is SIP-enabled.</span></span>

  - <span data-ttu-id="56f20-158">如果您仍然有問題，LRS 系統中收集**Trace.log**檔案從 d:\\追蹤\\LRSAdminLogs\\，然後將它傳送給您 LRS 支援連絡人。</span><span class="sxs-lookup"><span data-stu-id="56f20-158">If you are still having issues, collect the **Trace.log** file in the LRS system from D:\\Tracing\\LRSAdminLogs\\, and then send it to your LRS support contact.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

