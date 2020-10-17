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
ms.openlocfilehash: 0a33a5e9bb93371bdccac3c88b7a1c080e3efaa8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503680"
---
# <a name="validating-the-configuration-of-office-web-apps-server-in-lync-server-2013"></a><span data-ttu-id="475fb-102">驗證 Lync Server 2013 中的 Office Web Apps Server 設定</span><span class="sxs-lookup"><span data-stu-id="475fb-102">Validating the configuration of Office Web Apps Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="475fb-103">_**主題上次修改日期：** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="475fb-103">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="475fb-104">將 Office Web Apps Server 新增至拓撲之後，在發行該拓撲之後，您應該會在 Lync Server 事件記錄檔中看到兩個新的事件記錄事件。</span><span class="sxs-lookup"><span data-stu-id="475fb-104">After Office Web Apps Server has been added to the topology, and after that topology has been published, you should see two new event log events in the Lync Server event log.</span></span> <span data-ttu-id="475fb-105">首先，應新增 LS 資料 MCU 事件 (事件識別碼 41034) 。此事件會報告已探索到 Office Web Apps Server：</span><span class="sxs-lookup"><span data-stu-id="475fb-105">First, an LS Data MCU event (event ID 41034) should be added; this event will report that the Office Web Apps Server has been discovered:</span></span>

<span data-ttu-id="475fb-106">**已探索 Web 會議伺服器 Office Web Apps Server，PowerPoint 內容已啟用。**</span><span class="sxs-lookup"><span data-stu-id="475fb-106">**Web Conferencing Server Office Web Apps Server is discovered, PowerPoint content is enabled.**</span></span>

<span data-ttu-id="475fb-107">除了該之外，您還應該看到另一個 LS 資料 MCU 事件， (事件識別碼 41032) ，以報告回 URLs 的 Office Web Apps Server。</span><span class="sxs-lookup"><span data-stu-id="475fb-107">In addition to that you should see another LS Data MCU event (event ID 41032) that reports back Office Web Apps Server URLs.</span></span> <span data-ttu-id="475fb-108">例如，您應該會看到類似下列的內容：</span><span class="sxs-lookup"><span data-stu-id="475fb-108">For example, you should see something similar to this:</span></span>

<span data-ttu-id="475fb-109">**Web 會議伺服器 Office Web Apps Server discovery 已成功。**</span><span class="sxs-lookup"><span data-stu-id="475fb-109">**Web Conferencing Server Office Web Apps Server discovery has succeeded.**</span></span>

<span data-ttu-id="475fb-110">**Office Web Apps Server 內部簡報者頁面： https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed=**</span><span class="sxs-lookup"><span data-stu-id="475fb-110">**Office Web Apps Server internal presenter page: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed=**</span></span>

<span data-ttu-id="475fb-111">**Office Web Apps Server 內部出席者頁面： https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&=**</span><span class="sxs-lookup"><span data-stu-id="475fb-111">**Office Web Apps Server internal attendee page: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&=**</span></span>

<span data-ttu-id="475fb-112">**Office Web Apps Server 外部簡報者頁面： https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed**</span><span class="sxs-lookup"><span data-stu-id="475fb-112">**Office Web Apps Server external presenter page: https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed**</span></span>

<span data-ttu-id="475fb-113">**Office Web Apps Server 內部出席者頁面： https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&**</span><span class="sxs-lookup"><span data-stu-id="475fb-113">**Office Web Apps Server internal attendee page: https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&**</span></span>

<span data-ttu-id="475fb-114">如果您看到 LS 資料 MCU 事件，但事件識別碼為41033，表示 Office Web Apps Server discovery 失敗。</span><span class="sxs-lookup"><span data-stu-id="475fb-114">If you see an LS Data MCU event with the event ID of 41033 that means that Office Web Apps Server discovery has failed.</span></span> <span data-ttu-id="475fb-115">在此情況下，Microsoft Lync Server 2013 會視需要嘗試許多次數，以探索新設定的 Office Web Apps Server。</span><span class="sxs-lookup"><span data-stu-id="475fb-115">In that case, Microsoft Lync Server 2013 will try as many times as needed to discover the newly-configured Office Web Apps Server.</span></span> <span data-ttu-id="475fb-116">如果探索過程重複失敗，您應該移除拓撲檔中的 Office Web Apps Server、發佈更新的拓撲，然後在解決連接問題後，嘗試將 Office Web Apps Server 重新新增至拓撲。</span><span class="sxs-lookup"><span data-stu-id="475fb-116">If the discovery process fails repeatedly you should remove Office Web Apps Server from your topology document, publish the updated topology, and then try adding Office Web Apps Server back to the topology after the connectivity issues have been resolved.</span></span>

<span data-ttu-id="475fb-117">如果 Office Web Apps Server 似乎已正確設定，且已被探索程式識別，您可以在一對 Microsoft Lync 2013 用戶端之間共用 PowerPoint 簡報，以確認 Office Web Apps Server 的運作方式如預期般運作。</span><span class="sxs-lookup"><span data-stu-id="475fb-117">If Office Web Apps Server appears to be configured correctly and has been recognized by the discovery process you can verify that Office Web Apps Server is working as expected by sharing a PowerPoint presentation between a pair of Microsoft Lync 2013 clients.</span></span> <span data-ttu-id="475fb-118">如果使用者 A 可以載入及顯示 PowerPoint 簡報，而且使用者 B 可以加入會議，並查看該簡報之後，Office Web Apps Server 會正常運作。</span><span class="sxs-lookup"><span data-stu-id="475fb-118">If User A can load and display the PowerPoint presentation and if User B can then join the meeting and see that presentation then Office Web Apps Server is working.</span></span>

<span data-ttu-id="475fb-119">即使已正確設定 Office Web Apps Server，當您嘗試共用 PowerPoint 簡報時，可能會收到錯誤訊息「某些共用功能因伺服器連線問題而無法使用」。</span><span class="sxs-lookup"><span data-stu-id="475fb-119">Even if Office Web Apps Server appears to be configured correctly, you could potentially receive the error message “Some sharing features are unavailable due to server connectivity issues” when you try sharing a PowerPoint presentation.</span></span> <span data-ttu-id="475fb-120">如果您收到該錯誤訊息，您應該重新開機前端伺服器 (或與新 Office Web Apps Server 關聯的伺服器) 。</span><span class="sxs-lookup"><span data-stu-id="475fb-120">If you receive that error message you should restart the Front End server (or servers) associated with the new Office Web Apps Server.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

