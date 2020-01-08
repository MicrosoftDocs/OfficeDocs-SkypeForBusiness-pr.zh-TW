---
title: Lync Server 2013：使用 Lync Room System 系統管理 Web 入口網站
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using the Lync Room System Administrative Web Portal
ms:assetid: c387b2a3-3e42-4642-af72-88126ed2820f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743660(v=OCS.15)
ms:contentKeyID: 62268951
ms.date: 11/13/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2369cdde9d14275fddf007b5e073c748ce5a8906
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978226"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a><span data-ttu-id="bd803-102">在 Lync Server 2013 中使用 Lync Room System 系統管理 Web 入口網站</span><span class="sxs-lookup"><span data-stu-id="bd803-102">Using the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bd803-103">_**主題上次修改日期：** 2014-11-10_</span><span class="sxs-lookup"><span data-stu-id="bd803-103">_**Topic Last Modified:** 2014-11-10_</span></span>

<span data-ttu-id="bd803-104">在伺服器上部署 LRS 之後，您可以從瀏覽器登入 LRS 管理網頁入口網站，查看所有 LRS 聊天室的狀態。</span><span class="sxs-lookup"><span data-stu-id="bd803-104">After you deploy LRS on the server, you can check the status of all LRS rooms by signing into the LRS Administrative Web Portal from a browser.</span></span>

<div>

## <a name="sign-in"></a><span data-ttu-id="bd803-105">登錄</span><span class="sxs-lookup"><span data-stu-id="bd803-105">Sign in</span></span>

1.  <span data-ttu-id="bd803-106">流覽至下列 URL：</span><span class="sxs-lookup"><span data-stu-id="bd803-106">Browse to the following URL:</span></span>
    
    <span data-ttu-id="bd803-107">HTTPs://\<fe-伺服器\>/lrs</span><span class="sxs-lookup"><span data-stu-id="bd803-107">https://\<fe-server\>/lrs</span></span>

2.  <span data-ttu-id="bd803-108">輸入 LRSSupport 帳戶的認證，或是已新增至 LRSSupportAdminGroup 安全性群組的帳戶。</span><span class="sxs-lookup"><span data-stu-id="bd803-108">Enter the credentials for the LRSSupport account or an account that has been added to the LRSSupportAdminGroup security group.</span></span>

<span data-ttu-id="bd803-109">![Lync 會議室系統管理入口網站登入螢幕](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Lync 會議室系統管理入口網站登入畫面")</span><span class="sxs-lookup"><span data-stu-id="bd803-109">![Lync Room System Admin Portal Sign In screen](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Lync Room System Admin Portal Sign In screen")</span></span>

</div>

<div>

## <a name="lrs-administrative-web-portal-summary-page"></a><span data-ttu-id="bd803-110">LRS 系統管理網頁入口網站摘要頁面</span><span class="sxs-lookup"><span data-stu-id="bd803-110">LRS Administrative Web Portal Summary Page</span></span>

<span data-ttu-id="bd803-111">[摘要] 頁面提供伺服器上部署之所有 LRS 聊天室的下列資訊：</span><span class="sxs-lookup"><span data-stu-id="bd803-111">The summary page provides the following information for all of the LRS rooms deployed on the server:</span></span>

  - <span data-ttu-id="bd803-112">**標記**   管理員提供給聊天室的自訂名稱。</span><span class="sxs-lookup"><span data-stu-id="bd803-112">**Tag**   The custom name that the administrator gives to the room.</span></span> <span data-ttu-id="bd803-113">您可以按一下房間名稱，在入口網站中設定標籤。</span><span class="sxs-lookup"><span data-stu-id="bd803-113">The Tag can be set in the portal by clicking on the room name.</span></span>

  - <span data-ttu-id="bd803-114">**健康情況**   的健康情況，該房間是從聊天室的 [健康情況] 區段（在 [會議室設定] 頁面的 [健康情況] 區段中所示）衍生而來。</span><span class="sxs-lookup"><span data-stu-id="bd803-114">**Health**   The health status of the room, which is derived from the Aggregate Health status of the room, which is shown under the Health section of the Room Settings page.</span></span>

  - <span data-ttu-id="bd803-115">**[下一步會議**   ] 在排程下次會議的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="bd803-115">**Next Meeting**   The date and time the next meeting is scheduled.</span></span>

  - <span data-ttu-id="bd803-116">**LRS 版本、製造商、型號**   這些值是在 LRS 中預先設定。</span><span class="sxs-lookup"><span data-stu-id="bd803-116">**LRS Version, Manufacturer, Model**   These values are preset in LRS.</span></span> <span data-ttu-id="bd803-117">視製造商而定，這些欄位可能會保留空白。</span><span class="sxs-lookup"><span data-stu-id="bd803-117">Depending on the manufacturer, these fields might be left blank.</span></span>

  - <span data-ttu-id="bd803-118">**[上次**   重新整理] 會顯示最後一次重新整理網頁的時間。</span><span class="sxs-lookup"><span data-stu-id="bd803-118">**Last Refresh**   Displays the last time the webpage was refreshed.</span></span>

<span data-ttu-id="bd803-119">![Lync 會議室系統管理入口網站摘要查看](images/Dn743660.f829ce90-dd95-4725-bd94-6870c5dcf046(OCS.15).png "Lync 會議室系統管理入口網站摘要視圖")</span><span class="sxs-lookup"><span data-stu-id="bd803-119">![Lync Room System Admin Portal Summary View](images/Dn743660.f829ce90-dd95-4725-bd94-6870c5dcf046(OCS.15).png "Lync Room System Admin Portal Summary View")</span></span>

</div>

<div>

## <a name="lrs-room-information"></a><span data-ttu-id="bd803-120">LRS 會議室資訊</span><span class="sxs-lookup"><span data-stu-id="bd803-120">LRS Room Information</span></span>

<span data-ttu-id="bd803-121">入口網站的 [會議室資訊] 區段可讓您查看和設定個別的 LRS 會議室。</span><span class="sxs-lookup"><span data-stu-id="bd803-121">The Room Info section of the portal allows you to view and configure individual LRS rooms.</span></span> <span data-ttu-id="bd803-122">它包含四個區段：設定、詳細資料、疑難排解及健康情況。</span><span class="sxs-lookup"><span data-stu-id="bd803-122">It contains four sections: Settings, Details, Troubleshooting, and Health.</span></span>

<div>

## <a name="settings"></a><span data-ttu-id="bd803-123">設置</span><span class="sxs-lookup"><span data-stu-id="bd803-123">Settings</span></span>

<span data-ttu-id="bd803-124">在 [設定] 區段中，您可以設定聊天室的密碼、房間標籤及預設音量等級。</span><span class="sxs-lookup"><span data-stu-id="bd803-124">In the Settings section, you can set the password, room tag, and default volume levels for the room.</span></span> <span data-ttu-id="bd803-125">如果您設定這些設定，變更只會在您重新開機 LRS 主控台後進行複製。</span><span class="sxs-lookup"><span data-stu-id="bd803-125">If you configure these settings, the changes are replicated only after you restart the LRS console.</span></span> <span data-ttu-id="bd803-126">您只會看到版本15.12 及更新版本之 Lync 機房系統的系統更新設定。</span><span class="sxs-lookup"><span data-stu-id="bd803-126">You will only see System Updates settings for Lync Room Systems that are version 15.12 and later.</span></span>

<span data-ttu-id="bd803-127">![Lync 會議室系統管理入口網站室設定](images/Dn743660.ab162e19-41ac-4991-9b2a-92575aa53eda(OCS.15).png "Lync 會議室系統管理入口網站室設定")</span><span class="sxs-lookup"><span data-stu-id="bd803-127">![Lync Room System Admin Portal Room Settings](images/Dn743660.ab162e19-41ac-4991-9b2a-92575aa53eda(OCS.15).png "Lync Room System Admin Portal Room Settings")</span></span>

</div>

<div>

## <a name="details"></a><span data-ttu-id="bd803-128">詳細資料</span><span class="sxs-lookup"><span data-stu-id="bd803-128">Details</span></span>

<span data-ttu-id="bd803-129">[詳細資料] 區段提供 LRS 會議室設定的唯讀摘要，包括：上次重新整理的時間;下次會議;上次更新、維護和校準;預設喇叭、麥克風和鈴聲設定;新版SIP URI;螢幕數目及每個畫面的詳細資料;狀態和活動。</span><span class="sxs-lookup"><span data-stu-id="bd803-129">The Details section provides a read-only summary of the LRS room’s settings, including: the time of last refresh; next meeting; last updates, maintenance and calibration; default speaker, mic, and ringer settings; version; SIP URI; number of screens and details about each screen; status, and activity.</span></span>

<span data-ttu-id="bd803-130">![Lync 會議室系統管理入口網站詳細資料查看](images/Dn743660.2958bbba-db74-4670-a920-87fdfb2fc22d(OCS.15).png "Lync 會議室系統管理入口網站詳細資料檢視")</span><span class="sxs-lookup"><span data-stu-id="bd803-130">![Lync Room System Admin Portal Detail View](images/Dn743660.2958bbba-db74-4670-a920-87fdfb2fc22d(OCS.15).png "Lync Room System Admin Portal Detail View")</span></span>

</div>

<div>

## <a name="troubleshooting"></a><span data-ttu-id="bd803-131">疑難排解</span><span class="sxs-lookup"><span data-stu-id="bd803-131">Troubleshooting</span></span>

<span data-ttu-id="bd803-132">疑難排解一節可用來遠端收集記錄，並將它們儲存到指定的位置。</span><span class="sxs-lookup"><span data-stu-id="bd803-132">The Troubleshooting section can be used to remotely collect logs and save them to a specified location.</span></span> <span data-ttu-id="bd803-133">您也可以重新開機 LRS 主控台（LRS 使用者介面），或重新開機整個系統。</span><span class="sxs-lookup"><span data-stu-id="bd803-133">You can also restart the LRS console (LRS user interface) or restart the entire system.</span></span> <span data-ttu-id="bd803-134">若要收集記錄，請以指定的格式提供資料夾路徑，並確認資料夾擁有 LRS 電腦帳戶的寫入權限。</span><span class="sxs-lookup"><span data-stu-id="bd803-134">To collect logs, provide a folder path in the specified format and make sure that the folder has write permissions given to the LRS machine account.</span></span> <span data-ttu-id="bd803-135">如果記錄大小太大，可能需要最多5分鐘的時間來完成收集記錄。</span><span class="sxs-lookup"><span data-stu-id="bd803-135">If the log size is too big, it can take up to 5 minutes to finish collecting logs.</span></span> <span data-ttu-id="bd803-136">重新整理頁面會提供最新狀態。</span><span class="sxs-lookup"><span data-stu-id="bd803-136">Refreshing the page will give you the latest status.</span></span>

<span data-ttu-id="bd803-137">![Lync 會議室系統管理入口網站室記錄](images/Dn743660.749aee71-deaa-4ace-a146-fe2b349f0f42(OCS.15).png "Lync 室系統管理員入口網站房間記錄")</span><span class="sxs-lookup"><span data-stu-id="bd803-137">![Lync Room System Admin Portal Room Logging](images/Dn743660.749aee71-deaa-4ace-a146-fe2b349f0f42(OCS.15).png "Lync Room System Admin Portal Room Logging")</span></span>

</div>

<div>

## <a name="health"></a><span data-ttu-id="bd803-138">運行</span><span class="sxs-lookup"><span data-stu-id="bd803-138">Health</span></span>

<span data-ttu-id="bd803-139">[健康情況] 區段提供 Lync Server 連線、音訊裝置、視頻裝置、復原狀態及螢幕裝置的健康情況的視覺指示。</span><span class="sxs-lookup"><span data-stu-id="bd803-139">The Health section gives a visual indication of the health of the Lync Server connection, audio device, video device, resiliency state, and screen device.</span></span>

<span data-ttu-id="bd803-140">![Lync 會議室系統管理入口網站室健康情況](images/Dn743660.8cc644f8-8e3e-42d5-9079-045d8fe9daa7(OCS.15).png "Lync 室系統管理員入口網站健康情況")</span><span class="sxs-lookup"><span data-stu-id="bd803-140">![Lync Room System Admin Portal Room Health](images/Dn743660.8cc644f8-8e3e-42d5-9079-045d8fe9daa7(OCS.15).png "Lync Room System Admin Portal Room Health")</span></span>

</div>

</div>

<div>

## <a name="additional-notes-about-the-administrative-web-portal"></a><span data-ttu-id="bd803-141">有關系統管理網頁入口網站的其他注意事項</span><span class="sxs-lookup"><span data-stu-id="bd803-141">Additional Notes about the Administrative Web Portal</span></span>

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="bd803-142">設定變更只會在 LRS 系統重新開機後套用。</span><span class="sxs-lookup"><span data-stu-id="bd803-142">Setting changes are applied only after the LRS system is restarted.</span></span></P>
> <LI>
> <P><span data-ttu-id="bd803-143">如果 LRSApp 帳戶密碼到期，您將無法看到聊天室的狀態。</span><span class="sxs-lookup"><span data-stu-id="bd803-143">If the LRSApp account password expires, you will not be able to see the status of the rooms.</span></span> <span data-ttu-id="bd803-144">設定 LRSAppuser 帳戶密碼，讓它永不過期，或者請務必在接近到期時更新密碼。</span><span class="sxs-lookup"><span data-stu-id="bd803-144">Configure the LRSAppuser account password so that it never expires, or be sure to update the password when it’s near expiration.</span></span></P>
> <LI>
> <P><span data-ttu-id="bd803-145">僅限內部部署部署支援 LRS 系統管理網頁入口網站。</span><span class="sxs-lookup"><span data-stu-id="bd803-145">The LRS administrative web portal is supported for on-premises deployments only.</span></span></P></LI></UL>



</div>

</div>

<div>

## <a name="frequently-asked-questions"></a><span data-ttu-id="bd803-146">常見問題</span><span class="sxs-lookup"><span data-stu-id="bd803-146">Frequently Asked Questions</span></span>

<div>

## <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a><span data-ttu-id="bd803-147">為什麼我無法登入系統管理網頁入口網站？</span><span class="sxs-lookup"><span data-stu-id="bd803-147">Why can’t I sign in to the administrative web portal?</span></span>

  - <span data-ttu-id="bd803-148">當您開啟https://localhost/lrs時，您可以看到 [登入] 頁面，但是當您輸入認證時，就無法登入。</span><span class="sxs-lookup"><span data-stu-id="bd803-148">When you open https://localhost/lrs, you will be able to see the sign in page, but when you type in your credentials, you cannot sign in.</span></span> <span data-ttu-id="bd803-149">在這種情況下，您https://FQDNofFEserver/lrs必須開啟，才能登入管理網頁入口網站。</span><span class="sxs-lookup"><span data-stu-id="bd803-149">In this case, you must open https://FQDNofFEserver/lrs to sign in to the administrative web portal.</span></span>

  - <span data-ttu-id="bd803-150">如果您要存取系統管理網頁入口網站的電腦位於 [工作組] 中，則 "HTTP://" 將無法運作。</span><span class="sxs-lookup"><span data-stu-id="bd803-150">If the machine from which you are accessing the administrative web portal is in a workgroup, "http://" will not work.</span></span> <span data-ttu-id="bd803-151">請改用 "HTTPs"。</span><span class="sxs-lookup"><span data-stu-id="bd803-151">Use "https" instead.</span></span>

</div>

<div>

## <a name="why-cant-i-see-lrs-in-the-administrative-web-portal"></a><span data-ttu-id="bd803-152">為什麼在管理網頁入口網站中看不到 LRS？</span><span class="sxs-lookup"><span data-stu-id="bd803-152">Why can’t I see LRS in the administrative web portal?</span></span>

  - <span data-ttu-id="bd803-153">請確定您在部署中有 LRS 帳戶，並根據 LRS 的系統管理網頁入口網站部署建議來建立它們。</span><span class="sxs-lookup"><span data-stu-id="bd803-153">Make sure you have LRS accounts in your deployment and that they are created according to the LRS Administrative Web Portal deployment recommendations.</span></span> <span data-ttu-id="bd803-154">在 Lync server 上，確認已使用 Enable-CsMeetingRoom （而非啟用-Move-csuser）來預配 LRS 帳戶。</span><span class="sxs-lookup"><span data-stu-id="bd803-154">Make sure the LRS accounts are provisioned using Enable-CsMeetingRoom, not Enable-CsUser, on the Lync server.</span></span>

  - <span data-ttu-id="bd803-155">如果您已建立 LRS 帳戶，但在管理網頁入口網站中看不到帳戶，請使用已選取 [ **MeetingPortal** ] 元件的 Lync server 記錄工具收集伺服器記錄，然後將它們傳送到您的 LRS 支援連絡人。</span><span class="sxs-lookup"><span data-stu-id="bd803-155">If you have created LRS accounts and cannot see the accounts in administrative web portal, collect the server logs by using the Lync Server Logging tool with the **MeetingPortal** component selected, and then send them to your LRS support contact.</span></span>

</div>

<div>

## <a name="why-cant-i-see-the-status-of-lrs-in-the-administrative-web-portal"></a><span data-ttu-id="bd803-156">為什麼在管理網頁入口網站中看不到 LRS 的狀態？</span><span class="sxs-lookup"><span data-stu-id="bd803-156">Why can’t I see the status of LRS in the administrative web portal?</span></span>

  - <span data-ttu-id="bd803-157">確認 LRSApp 使用者帳戶已啟用 SIP。</span><span class="sxs-lookup"><span data-stu-id="bd803-157">Make sure that the LRSApp user account is SIP-enabled.</span></span>

  - <span data-ttu-id="bd803-158">如果您仍有問題，請從 D：\\\\LRS 系統中收集\\ **Trace .log**檔案，並將它傳送到您的 LRS 支援連絡人。</span><span class="sxs-lookup"><span data-stu-id="bd803-158">If you are still having issues, collect the **Trace.log** file in the LRS system from D:\\Tracing\\LRSAdminLogs\\, and then send it to your LRS support contact.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

