---
title: Lync Server 2013：驗證 Office Web Apps Server 的設定
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
ms.openlocfilehash: 541929233eff5e401b3998aa84e463e2640378c0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763567"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-the-configuration-of-office-web-apps-server-in-lync-server-2013"></a><span data-ttu-id="c6749-102">驗證 Lync Server 2013 中的 Office Web Apps Server 設定</span><span class="sxs-lookup"><span data-stu-id="c6749-102">Validating the configuration of Office Web Apps Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6749-103">_**主題上次修改日期：** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="c6749-103">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="c6749-104">在已將 Office Web Apps 伺服器新增到拓撲之後，且在該拓撲發佈之後，您應該會在 Lync 伺服器事件日誌中看到兩個新的事件記錄事件。</span><span class="sxs-lookup"><span data-stu-id="c6749-104">After Office Web Apps Server has been added to the topology, and after that topology has been published, you should see two new event log events in the Lync Server event log.</span></span> <span data-ttu-id="c6749-105">首先，應該新增 LS 資料 MCU 事件（事件 ID 41034）;這個事件會報告已發現 Office Web Apps 伺服器：</span><span class="sxs-lookup"><span data-stu-id="c6749-105">First, an LS Data MCU event (event ID 41034) should be added; this event will report that the Office Web Apps Server has been discovered:</span></span>

<span data-ttu-id="c6749-106">**已發現 Web 會議 Server Office Web Apps Server，已啟用 PowerPoint 內容。**</span><span class="sxs-lookup"><span data-stu-id="c6749-106">**Web Conferencing Server Office Web Apps Server is discovered, PowerPoint content is enabled.**</span></span>

<span data-ttu-id="c6749-107">此外，您還會看到另一個 [LS 資料 MCU] 事件（事件 ID 41032），該事件會傳回 Office Web Apps Server Url。</span><span class="sxs-lookup"><span data-stu-id="c6749-107">In addition to that you should see another LS Data MCU event (event ID 41032) that reports back Office Web Apps Server URLs.</span></span> <span data-ttu-id="c6749-108">例如，您應該會看到類似以下的內容：</span><span class="sxs-lookup"><span data-stu-id="c6749-108">For example, you should see something similar to this:</span></span>

<span data-ttu-id="c6749-109">**網路會議服務器 Office Web Apps 伺服器探索已成功完成。**</span><span class="sxs-lookup"><span data-stu-id="c6749-109">**Web Conferencing Server Office Web Apps Server discovery has succeeded.**</span></span>

<span data-ttu-id="c6749-110">**Office Web Apps Server 內部簡報者頁面：https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed=**</span><span class="sxs-lookup"><span data-stu-id="c6749-110">**Office Web Apps Server internal presenter page: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed=**</span></span>

<span data-ttu-id="c6749-111">**Office Web Apps 伺服器內部出席者頁面：https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&=**</span><span class="sxs-lookup"><span data-stu-id="c6749-111">**Office Web Apps Server internal attendee page: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&=**</span></span>

<span data-ttu-id="c6749-112">**Office Web Apps Server 外部簡報者頁面：https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed**</span><span class="sxs-lookup"><span data-stu-id="c6749-112">**Office Web Apps Server external presenter page: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed**</span></span>

<span data-ttu-id="c6749-113">**Office Web Apps 伺服器內部出席者頁面：https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&**</span><span class="sxs-lookup"><span data-stu-id="c6749-113">**Office Web Apps Server internal attendee page: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&**</span></span>

<span data-ttu-id="c6749-114">如果您看到 LS 資料 MCU 事件，且事件 ID 為41033，表示 Office Web Apps Server 發現失敗。</span><span class="sxs-lookup"><span data-stu-id="c6749-114">If you see an LS Data MCU event with the event ID of 41033 that means that Office Web Apps Server discovery has failed.</span></span> <span data-ttu-id="c6749-115">在這種情況下，Microsoft Lync Server 2013 會根據需要嘗試許多次數，以探索新設定的 Office Web Apps 伺服器。</span><span class="sxs-lookup"><span data-stu-id="c6749-115">In that case, Microsoft Lync Server 2013 will try as many times as needed to discover the newly-configured Office Web Apps Server.</span></span> <span data-ttu-id="c6749-116">如果探索程式重複失敗，您應該從拓撲檔中移除 Office Web Apps 伺服器、發佈更新的拓撲，然後在連線問題解決之後，嘗試將 Office Web Apps 伺服器新增到拓撲結構。</span><span class="sxs-lookup"><span data-stu-id="c6749-116">If the discovery process fails repeatedly you should remove Office Web Apps Server from your topology document, publish the updated topology, and then try adding Office Web Apps Server back to the topology after the connectivity issues have been resolved.</span></span>

<span data-ttu-id="c6749-117">如果 Office Web Apps 伺服器出現正確設定，且已被探索程式辨識，您可以在一對 Microsoft Lync 2013 用戶端之間共用 PowerPoint 簡報，以驗證 Office Web Apps 伺服器是否在正常運作。</span><span class="sxs-lookup"><span data-stu-id="c6749-117">If Office Web Apps Server appears to be configured correctly and has been recognized by the discovery process you can verify that Office Web Apps Server is working as expected by sharing a PowerPoint presentation between a pair of Microsoft Lync 2013 clients.</span></span> <span data-ttu-id="c6749-118">如果使用者 A 可以載入並顯示 PowerPoint 簡報，而使用者 B 可以接著加入會議，然後查看該簡報，則 Office Web Apps Server 就能正常運作。</span><span class="sxs-lookup"><span data-stu-id="c6749-118">If User A can load and display the PowerPoint presentation and if User B can then join the meeting and see that presentation then Office Web Apps Server is working.</span></span>

<span data-ttu-id="c6749-119">即使 Office Web Apps 伺服器的設定正確，您也可能會在嘗試共用 PowerPoint 簡報時，收到「由於伺服器連線問題，有些共用功能無法使用」錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="c6749-119">Even if Office Web Apps Server appears to be configured correctly, you could potentially receive the error message “Some sharing features are unavailable due to server connectivity issues” when you try sharing a PowerPoint presentation.</span></span> <span data-ttu-id="c6749-120">如果您收到該錯誤訊息，您應該重新開機與新的 Office Web Apps 伺服器相關聯的前端伺服器（或伺服器）。</span><span class="sxs-lookup"><span data-stu-id="c6749-120">If you receive that error message you should restart the Front End server (or servers) associated with the new Office Web Apps Server.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

