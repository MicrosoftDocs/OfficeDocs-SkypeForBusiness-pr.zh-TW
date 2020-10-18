---
title: Lync Server 2013：使用 Lync 會議室系統管理 Web 入口網站
description: Lync Server 2013：使用 Lync 會議室系統管理 Web 入口網站。
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
ms.openlocfilehash: 28c29677080bf081eae0fa4227e4cb56ccac697b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579649"
---
# <a name="using-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a><span data-ttu-id="a94f8-103">在 Lync Server 2013 中使用 Lync 會議室系統管理 Web 入口網站</span><span class="sxs-lookup"><span data-stu-id="a94f8-103">Using the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a94f8-104">_**主題上次修改日期：** 2014-11-10_</span><span class="sxs-lookup"><span data-stu-id="a94f8-104">_**Topic Last Modified:** 2014-11-10_</span></span>

<span data-ttu-id="a94f8-105">在伺服器上部署 LRS 之後，您可以在瀏覽器中登入 LRS 管理網頁入口網站，以檢查所有 LRS 聊天室的狀態。</span><span class="sxs-lookup"><span data-stu-id="a94f8-105">After you deploy LRS on the server, you can check the status of all LRS rooms by signing into the LRS Administrative Web Portal from a browser.</span></span>

<div>

## <a name="sign-in"></a><span data-ttu-id="a94f8-106">登入</span><span class="sxs-lookup"><span data-stu-id="a94f8-106">Sign in</span></span>

1.  <span data-ttu-id="a94f8-107">流覽至下列 URL:</span><span class="sxs-lookup"><span data-stu-id="a94f8-107">Browse to the following URL:</span></span>
    
    <span data-ttu-id="a94f8-108">HTTPs:// \<fe-server\> /lrs</span><span class="sxs-lookup"><span data-stu-id="a94f8-108">https://\<fe-server\>/lrs</span></span>

2.  <span data-ttu-id="a94f8-109">輸入 LRSSupport 帳戶的認證，或已新增至 LRSSupportAdminGroup 安全性群組的帳戶。</span><span class="sxs-lookup"><span data-stu-id="a94f8-109">Enter the credentials for the LRSSupport account or an account that has been added to the LRSSupportAdminGroup security group.</span></span>

<span data-ttu-id="a94f8-110">![Lync 會議室系統管理入口網站登錄畫面](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Lync 會議室系統管理入口網站登錄畫面")</span><span class="sxs-lookup"><span data-stu-id="a94f8-110">![Lync Room System Admin Portal Sign In screen](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Lync Room System Admin Portal Sign In screen")</span></span>

</div>

<div>

## <a name="lrs-administrative-web-portal-summary-page"></a><span data-ttu-id="a94f8-111">LRS 系統管理 Web 入口網站摘要頁面</span><span class="sxs-lookup"><span data-stu-id="a94f8-111">LRS Administrative Web Portal Summary Page</span></span>

<span data-ttu-id="a94f8-112">[摘要] 頁面針對伺服器上部署的所有 LRS 聊天室，提供下列資訊：</span><span class="sxs-lookup"><span data-stu-id="a94f8-112">The summary page provides the following information for all of the LRS rooms deployed on the server:</span></span>

  - <span data-ttu-id="a94f8-113">**標記**    管理員提供給會議室的自訂名稱。</span><span class="sxs-lookup"><span data-stu-id="a94f8-113">**Tag**   The custom name that the administrator gives to the room.</span></span> <span data-ttu-id="a94f8-114">您可以在入口網站中，按一下會議室名稱以設定標記。</span><span class="sxs-lookup"><span data-stu-id="a94f8-114">The Tag can be set in the portal by clicking on the room name.</span></span>

  - <span data-ttu-id="a94f8-115">**健全狀況**    會議室的健全狀況狀態，它是由聊天室的合計健康狀態所組成，它會顯示在 [會議室設定] 頁面的 [健康情況] 區段下。</span><span class="sxs-lookup"><span data-stu-id="a94f8-115">**Health**   The health status of the room, which is derived from the Aggregate Health status of the room, which is shown under the Health section of the Room Settings page.</span></span>

  - <span data-ttu-id="a94f8-116">**下一個會議**    排定下一個會議的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="a94f8-116">**Next Meeting**   The date and time the next meeting is scheduled.</span></span>

  - <span data-ttu-id="a94f8-117">**LRS Version，Manufacturer，Model**    這些值是預先設定的 LRS。</span><span class="sxs-lookup"><span data-stu-id="a94f8-117">**LRS Version, Manufacturer, Model**   These values are preset in LRS.</span></span> <span data-ttu-id="a94f8-118">視製造商而定，這些欄位可能會保留空白。</span><span class="sxs-lookup"><span data-stu-id="a94f8-118">Depending on the manufacturer, these fields might be left blank.</span></span>

  - <span data-ttu-id="a94f8-119">**上次重新整理**    顯示重新整理網頁的最後時間。</span><span class="sxs-lookup"><span data-stu-id="a94f8-119">**Last Refresh**   Displays the last time the webpage was refreshed.</span></span>

<span data-ttu-id="a94f8-120">![Lync 會議室系統管理員入口網站摘要視圖](images/Dn743660.f829ce90-dd95-4725-bd94-6870c5dcf046(OCS.15).png "Lync 會議室系統管理員入口網站摘要視圖")</span><span class="sxs-lookup"><span data-stu-id="a94f8-120">![Lync Room System Admin Portal Summary View](images/Dn743660.f829ce90-dd95-4725-bd94-6870c5dcf046(OCS.15).png "Lync Room System Admin Portal Summary View")</span></span>

</div>

<div>

## <a name="lrs-room-information"></a><span data-ttu-id="a94f8-121">LRS 會議室資訊</span><span class="sxs-lookup"><span data-stu-id="a94f8-121">LRS Room Information</span></span>

<span data-ttu-id="a94f8-122">入口網站的 [聊天室資訊] 區段可讓您查看及設定個別的 LRS 聊天室。</span><span class="sxs-lookup"><span data-stu-id="a94f8-122">The Room Info section of the portal allows you to view and configure individual LRS rooms.</span></span> <span data-ttu-id="a94f8-123">包含四個區段：設定、詳細資料、疑難排解及健康情況。</span><span class="sxs-lookup"><span data-stu-id="a94f8-123">It contains four sections: Settings, Details, Troubleshooting, and Health.</span></span>

<div>

## <a name="settings"></a><span data-ttu-id="a94f8-124">設定</span><span class="sxs-lookup"><span data-stu-id="a94f8-124">Settings</span></span>

<span data-ttu-id="a94f8-125">在 [設定] 區段中，您可以設定會議室的密碼、會議室標記和預設磁片區層級。</span><span class="sxs-lookup"><span data-stu-id="a94f8-125">In the Settings section, you can set the password, room tag, and default volume levels for the room.</span></span> <span data-ttu-id="a94f8-126">如果您設定這些設定，則只有在您重新開機 LRS 主控台之後才會複製變更。</span><span class="sxs-lookup"><span data-stu-id="a94f8-126">If you configure these settings, the changes are replicated only after you restart the LRS console.</span></span> <span data-ttu-id="a94f8-127">您只會看到版本15.12 和更新版本的 Lync 會議室系統的系統更新設定。</span><span class="sxs-lookup"><span data-stu-id="a94f8-127">You will only see System Updates settings for Lync Room Systems that are version 15.12 and later.</span></span>

<span data-ttu-id="a94f8-128">![Lync 會議室系統管理入口網站室設定](images/Dn743660.ab162e19-41ac-4991-9b2a-92575aa53eda(OCS.15).png "Lync 會議室系統管理入口網站室設定")</span><span class="sxs-lookup"><span data-stu-id="a94f8-128">![Lync Room System Admin Portal Room Settings](images/Dn743660.ab162e19-41ac-4991-9b2a-92575aa53eda(OCS.15).png "Lync Room System Admin Portal Room Settings")</span></span>

</div>

<div>

## <a name="details"></a><span data-ttu-id="a94f8-129">詳細資料</span><span class="sxs-lookup"><span data-stu-id="a94f8-129">Details</span></span>

<span data-ttu-id="a94f8-130">[詳細資料] 區段提供 LRS 會議室設定的唯讀摘要，包括：上次重新整理的時間;下一個會議;上次更新、維護和校準;預設的喇叭、mic 及鈴聲設定;版本SIP URI;每個畫面的畫面數目及詳細資料;狀態和活動。</span><span class="sxs-lookup"><span data-stu-id="a94f8-130">The Details section provides a read-only summary of the LRS room’s settings, including: the time of last refresh; next meeting; last updates, maintenance and calibration; default speaker, mic, and ringer settings; version; SIP URI; number of screens and details about each screen; status, and activity.</span></span>

<span data-ttu-id="a94f8-131">![Lync 會議室系統管理員入口網站詳細資料檢視](images/Dn743660.2958bbba-db74-4670-a920-87fdfb2fc22d(OCS.15).png "Lync 會議室系統管理員入口網站詳細資料檢視")</span><span class="sxs-lookup"><span data-stu-id="a94f8-131">![Lync Room System Admin Portal Detail View](images/Dn743660.2958bbba-db74-4670-a920-87fdfb2fc22d(OCS.15).png "Lync Room System Admin Portal Detail View")</span></span>

</div>

<div>

## <a name="troubleshooting"></a><span data-ttu-id="a94f8-132">疑難排解</span><span class="sxs-lookup"><span data-stu-id="a94f8-132">Troubleshooting</span></span>

<span data-ttu-id="a94f8-133">疑難排解區段可用於遠端收集記錄，並將其儲存到指定的位置。</span><span class="sxs-lookup"><span data-stu-id="a94f8-133">The Troubleshooting section can be used to remotely collect logs and save them to a specified location.</span></span> <span data-ttu-id="a94f8-134">您也可以重新開機 LRS 主控台 (LRS 使用者介面) 或重新開機整個系統。</span><span class="sxs-lookup"><span data-stu-id="a94f8-134">You can also restart the LRS console (LRS user interface) or restart the entire system.</span></span> <span data-ttu-id="a94f8-135">若要收集記錄檔，請提供指定格式的資料夾路徑，並確定資料夾具有 LRS 電腦帳戶的寫入權限。</span><span class="sxs-lookup"><span data-stu-id="a94f8-135">To collect logs, provide a folder path in the specified format and make sure that the folder has write permissions given to the LRS machine account.</span></span> <span data-ttu-id="a94f8-136">如果記錄檔的大小過大，則最多可能需要5分鐘的時間來收集記錄檔。</span><span class="sxs-lookup"><span data-stu-id="a94f8-136">If the log size is too big, it can take up to 5 minutes to finish collecting logs.</span></span> <span data-ttu-id="a94f8-137">重新整理頁面可提供您最新的狀態。</span><span class="sxs-lookup"><span data-stu-id="a94f8-137">Refreshing the page will give you the latest status.</span></span>

<span data-ttu-id="a94f8-138">![Lync 會議室系統管理入口網站室記錄](images/Dn743660.749aee71-deaa-4ace-a146-fe2b349f0f42(OCS.15).png "Lync 會議室系統管理入口網站室記錄")</span><span class="sxs-lookup"><span data-stu-id="a94f8-138">![Lync Room System Admin Portal Room Logging](images/Dn743660.749aee71-deaa-4ace-a146-fe2b349f0f42(OCS.15).png "Lync Room System Admin Portal Room Logging")</span></span>

</div>

<div>

## <a name="health"></a><span data-ttu-id="a94f8-139">健康情況</span><span class="sxs-lookup"><span data-stu-id="a94f8-139">Health</span></span>

<span data-ttu-id="a94f8-140">「狀況」區段提供 Lync Server 連線、音訊裝置、影片裝置、恢復狀態及螢幕裝置狀況的視覺指示。</span><span class="sxs-lookup"><span data-stu-id="a94f8-140">The Health section gives a visual indication of the health of the Lync Server connection, audio device, video device, resiliency state, and screen device.</span></span>

<span data-ttu-id="a94f8-141">![Lync 會議室系統管理入口網站室健康情況](images/Dn743660.8cc644f8-8e3e-42d5-9079-045d8fe9daa7(OCS.15).png "Lync 會議室系統管理入口網站室健康情況")</span><span class="sxs-lookup"><span data-stu-id="a94f8-141">![Lync Room System Admin Portal Room Health](images/Dn743660.8cc644f8-8e3e-42d5-9079-045d8fe9daa7(OCS.15).png "Lync Room System Admin Portal Room Health")</span></span>

</div>

</div>

<div>

## <a name="additional-notes-about-the-administrative-web-portal"></a><span data-ttu-id="a94f8-142">關於系統管理 Web 入口網站的其他注意事項</span><span class="sxs-lookup"><span data-stu-id="a94f8-142">Additional Notes about the Administrative Web Portal</span></span>

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="a94f8-143">只有在重新開機 LRS 系統之後，才會套用設定變更。</span><span class="sxs-lookup"><span data-stu-id="a94f8-143">Setting changes are applied only after the LRS system is restarted.</span></span></P>
> <LI>
> <P><span data-ttu-id="a94f8-144">如果 LRSApp 帳戶密碼到期，您就無法看到聊天室的狀態。</span><span class="sxs-lookup"><span data-stu-id="a94f8-144">If the LRSApp account password expires, you will not be able to see the status of the rooms.</span></span> <span data-ttu-id="a94f8-145">設定 LRSAppuser 帳戶密碼，使其永不到期，或務必在密碼即將到期時更新。</span><span class="sxs-lookup"><span data-stu-id="a94f8-145">Configure the LRSAppuser account password so that it never expires, or be sure to update the password when it’s near expiration.</span></span></P>
> <LI>
> <P><span data-ttu-id="a94f8-146">僅限內部部署部署支援 LRS 系統管理 web 入口網站。</span><span class="sxs-lookup"><span data-stu-id="a94f8-146">The LRS administrative web portal is supported for on-premises deployments only.</span></span></P></LI></UL>



</div>

</div>

<div>

## <a name="frequently-asked-questions"></a><span data-ttu-id="a94f8-147">常見問題集</span><span class="sxs-lookup"><span data-stu-id="a94f8-147">Frequently Asked Questions</span></span>

<div>

## <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a><span data-ttu-id="a94f8-148">為什麼我無法登入管理網頁入口網站？</span><span class="sxs-lookup"><span data-stu-id="a94f8-148">Why can’t I sign in to the administrative web portal?</span></span>

  - <span data-ttu-id="a94f8-149">當您開啟時 https://localhost/lrs ，您可以看到 [登入] 頁面，但是當您輸入您的認證時，您無法登入。</span><span class="sxs-lookup"><span data-stu-id="a94f8-149">When you open https://localhost/lrs, you will be able to see the sign in page, but when you type in your credentials, you cannot sign in.</span></span> <span data-ttu-id="a94f8-150">在此情況下，您必須先開啟 https://FQDNofFEserver/lrs 以登入管理 web 入口網站。</span><span class="sxs-lookup"><span data-stu-id="a94f8-150">In this case, you must open https://FQDNofFEserver/lrs to sign in to the administrative web portal.</span></span>

  - <span data-ttu-id="a94f8-151">如果您用來存取管理網頁入口網站的機器是在工作組中，則 "HTTP://" 將無法運作。</span><span class="sxs-lookup"><span data-stu-id="a94f8-151">If the machine from which you are accessing the administrative web portal is in a workgroup, "http://" will not work.</span></span> <span data-ttu-id="a94f8-152">請改為使用「HTTPs」。</span><span class="sxs-lookup"><span data-stu-id="a94f8-152">Use "https" instead.</span></span>

</div>

<div>

## <a name="why-cant-i-see-lrs-in-the-administrative-web-portal"></a><span data-ttu-id="a94f8-153">為什麼我無法在管理網頁入口網站中看到 LRS？</span><span class="sxs-lookup"><span data-stu-id="a94f8-153">Why can’t I see LRS in the administrative web portal?</span></span>

  - <span data-ttu-id="a94f8-154">請確定您的部署中有 LRS 帳戶，且這些帳戶是根據 LRS 系統管理 Web 入口網站部署建議所建立。</span><span class="sxs-lookup"><span data-stu-id="a94f8-154">Make sure you have LRS accounts in your deployment and that they are created according to the LRS Administrative Web Portal deployment recommendations.</span></span> <span data-ttu-id="a94f8-155">請確定已使用 Lync server 上的 Enable-CsMeetingRoom，而不是啟用-Get-csuser 來布建 LRS 帳戶。</span><span class="sxs-lookup"><span data-stu-id="a94f8-155">Make sure the LRS accounts are provisioned using Enable-CsMeetingRoom, not Enable-CsUser, on the Lync server.</span></span>

  - <span data-ttu-id="a94f8-156">如果您已建立 LRS 帳戶，但在管理 web 入口網站中看不到帳戶，請使用 Lync Server 記錄工具（選取 [ **MeetingPortal** ] 元件）來收集伺服器記錄，然後將其傳送給 LRS 支援連絡人。</span><span class="sxs-lookup"><span data-stu-id="a94f8-156">If you have created LRS accounts and cannot see the accounts in administrative web portal, collect the server logs by using the Lync Server Logging tool with the **MeetingPortal** component selected, and then send them to your LRS support contact.</span></span>

</div>

<div>

## <a name="why-cant-i-see-the-status-of-lrs-in-the-administrative-web-portal"></a><span data-ttu-id="a94f8-157">為什麼我無法在管理網頁入口網站中看到 LRS 的狀態？</span><span class="sxs-lookup"><span data-stu-id="a94f8-157">Why can’t I see the status of LRS in the administrative web portal?</span></span>

  - <span data-ttu-id="a94f8-158">請確定 LRSApp 的使用者帳戶已 SIP-enabled。</span><span class="sxs-lookup"><span data-stu-id="a94f8-158">Make sure that the LRSApp user account is SIP-enabled.</span></span>

  - <span data-ttu-id="a94f8-159">如果仍有問題，請從 D：追蹤 LRSAdminLogs 收集 LRS 系統中的 **Trace .log** 檔案 \\ \\ \\ ，然後將它傳送給 LRS 支援連絡人。</span><span class="sxs-lookup"><span data-stu-id="a94f8-159">If you are still having issues, collect the **Trace.log** file in the LRS system from D:\\Tracing\\LRSAdminLogs\\, and then send it to your LRS support contact.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

