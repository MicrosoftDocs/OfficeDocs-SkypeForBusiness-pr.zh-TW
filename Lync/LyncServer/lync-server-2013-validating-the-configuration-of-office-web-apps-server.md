---
title: Lync Server 2013： 驗證 Office Web Apps Server 的設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating the configuration of Office Web Apps Server
ms:assetid: f6e8ecbf-305d-4a13-92d0-b61dbd82b0ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205393(v=OCS.15)
ms:contentKeyID: 48185859
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 068c3fcfd33668918eb330b64d816ceca818de27
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211819"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="validating-the-configuration-of-office-web-apps-server-in-lync-server-2013"></a><span data-ttu-id="584a1-102">驗證 Lync Server 2013 中的 Office Web Apps Server 的設定</span><span class="sxs-lookup"><span data-stu-id="584a1-102">Validating the configuration of Office Web Apps Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="584a1-103">_**上次修改主題：** 2014年-04-22_</span><span class="sxs-lookup"><span data-stu-id="584a1-103">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="584a1-104">Office Web Apps Server 已新增至拓撲，並發佈該拓撲之後，您應該會看到兩個新 Lync Server 事件記錄檔中的事件記錄檔事件。</span><span class="sxs-lookup"><span data-stu-id="584a1-104">After Office Web Apps Server has been added to the topology, and after that topology has been published, you should see two new event log events in the Lync Server event log.</span></span> <span data-ttu-id="584a1-105">首先，您應該新增 LS 資料 MCU 事件 （事件識別碼 41034）;此事件會報告已探索到 Office Web Apps Server:</span><span class="sxs-lookup"><span data-stu-id="584a1-105">First, an LS Data MCU event (event ID 41034) should be added; this event will report that the Office Web Apps Server has been discovered:</span></span>

<span data-ttu-id="584a1-106">**發現 web 會議伺服器 Office Web Apps Server 時，已啟用 PowerPoint 內容。**</span><span class="sxs-lookup"><span data-stu-id="584a1-106">**Web Conferencing Server Office Web Apps Server is discovered, PowerPoint content is enabled.**</span></span>

<span data-ttu-id="584a1-107">除了為，您應該會看到另一個 LS 資料 MCU （事件識別碼 41032） 報告事件的回 Office Web Apps Server Url。</span><span class="sxs-lookup"><span data-stu-id="584a1-107">In addition to that you should see another LS Data MCU event (event ID 41032) that reports back Office Web Apps Server URLs.</span></span> <span data-ttu-id="584a1-108">例如，您應該會看到類似：</span><span class="sxs-lookup"><span data-stu-id="584a1-108">For example, you should see something similar to this:</span></span>

<span data-ttu-id="584a1-109">**Web 會議伺服器 Office Web Apps Server 探索作業順利完成。**</span><span class="sxs-lookup"><span data-stu-id="584a1-109">**Web Conferencing Server Office Web Apps Server discovery has succeeded.**</span></span>

<span data-ttu-id="584a1-110">**Office Web Apps Server 內部簡報者] 頁面上：https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed=**</span><span class="sxs-lookup"><span data-stu-id="584a1-110">**Office Web Apps Server internal presenter page: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed=**</span></span>

<span data-ttu-id="584a1-111">**Office Web Apps Server 內部出席者頁面：https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&=**</span><span class="sxs-lookup"><span data-stu-id="584a1-111">**Office Web Apps Server internal attendee page: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&=**</span></span>

<span data-ttu-id="584a1-112">**Office Web Apps Server 外部簡報者] 頁面上：https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed**</span><span class="sxs-lookup"><span data-stu-id="584a1-112">**Office Web Apps Server external presenter page: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed**</span></span>

<span data-ttu-id="584a1-113">**Office Web Apps Server 內部出席者頁面：https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&**</span><span class="sxs-lookup"><span data-stu-id="584a1-113">**Office Web Apps Server internal attendee page: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&**</span></span>

<span data-ttu-id="584a1-114">如果您看到的 41033 事件 id，表示該 Office Web Apps Server 探索 LS 資料 MCU 事件失敗。</span><span class="sxs-lookup"><span data-stu-id="584a1-114">If you see an LS Data MCU event with the event ID of 41033 that means that Office Web Apps Server discovery has failed.</span></span> <span data-ttu-id="584a1-115">在此情況下，Microsoft Lync Server 2013 會嘗試為探索新設定的 Office Web Apps Server 所需的次數。</span><span class="sxs-lookup"><span data-stu-id="584a1-115">In that case, Microsoft Lync Server 2013 will try as many times as needed to discover the newly-configured Office Web Apps Server.</span></span> <span data-ttu-id="584a1-116">探索程序便會重複替換失敗時您應該移除您的拓撲文件中的 Office Web Apps Server、 發佈更新過的拓撲，並再重試連線問題都已解決後，Office Web Apps Server 新增回拓撲。</span><span class="sxs-lookup"><span data-stu-id="584a1-116">If the discovery process fails repeatedly you should remove Office Web Apps Server from your topology document, publish the updated topology, and then try adding Office Web Apps Server back to the topology after the connectivity issues have been resolved.</span></span>

<span data-ttu-id="584a1-117">如果 Office Web Apps Server 出現正確設定，且具有已辨識的探索程序可以確認 Office Web Apps Server 是否如預期藉由共用 PowerPoint 簡報的 Microsoft Lync 2013 用戶端對之間運作。</span><span class="sxs-lookup"><span data-stu-id="584a1-117">If Office Web Apps Server appears to be configured correctly and has been recognized by the discovery process you can verify that Office Web Apps Server is working as expected by sharing a PowerPoint presentation between a pair of Microsoft Lync 2013 clients.</span></span> <span data-ttu-id="584a1-118">如果使用者 A 可以載入並顯示在 PowerPoint 簡報，並且使用者 B 可以再加入會議，請參閱該簡報使用 Office Web Apps Server。</span><span class="sxs-lookup"><span data-stu-id="584a1-118">If User A can load and display the PowerPoint presentation and if User B can then join the meeting and see that presentation then Office Web Apps Server is working.</span></span>

<span data-ttu-id="584a1-119">即使 Office Web Apps Server 出現正確設定，您無法可能會收到錯誤訊息 「 一些共用功能是否因伺服器連線問題而無法使用 」 當您嘗試共用 PowerPoint 簡報。</span><span class="sxs-lookup"><span data-stu-id="584a1-119">Even if Office Web Apps Server appears to be configured correctly, you could potentially receive the error message “Some sharing features are unavailable due to server connectivity issues” when you try sharing a PowerPoint presentation.</span></span> <span data-ttu-id="584a1-120">如果您收到您應該重新啟動前端 （或多部伺服器） 與新的 Office Web Apps Server 相關聯的錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="584a1-120">If you receive that error message you should restart the Front End server (or servers) associated with the new Office Web Apps Server.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

