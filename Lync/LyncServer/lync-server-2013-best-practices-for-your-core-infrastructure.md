---
title: Lync Server 2013： 的核心基礎結構的最佳作法
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for your core infrastructure in Lync Server 2013
ms:assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518328(v=OCS.15)
ms:contentKeyID: 61071242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 876a4de1357786e2d5089fdc632002107a6c7cc2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150732"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="best-practices-for-your-core-infrastructure-in-lync-server-2013"></a><span data-ttu-id="6ae9c-102">您在 Lync Server 2013 中的核心基礎結構的最佳做法</span><span class="sxs-lookup"><span data-stu-id="6ae9c-102">Best practices for your core infrastructure in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6ae9c-103">_**上次修改主題：** 2014年-01-27_</span><span class="sxs-lookup"><span data-stu-id="6ae9c-103">_**Topic Last Modified:** 2014-01-27_</span></span>

<span data-ttu-id="6ae9c-104">您可能已經採取一些步驟，包括透過確保硬體備份、避免電源中斷、例行性地安裝安全性更新與防毒措施，以及監控伺服器活動等作法，為您的系統設計容錯機制。</span><span class="sxs-lookup"><span data-stu-id="6ae9c-104">You have probably already taken steps to design fault tolerance in your system, using practices such as ensuring hardware redundancy, guarding against power loss, routinely installing security updates and antivirus measures, and Monitoring Server activity.</span></span> <span data-ttu-id="6ae9c-105">這些作法特地列出您的 Microsoft Lync Server 2013 基礎結構，不僅整個網路。</span><span class="sxs-lookup"><span data-stu-id="6ae9c-105">These practices benefit not only your Microsoft Lync Server 2013 infrastructure, but also your entire network.</span></span> <span data-ttu-id="6ae9c-106">如果您未實作這些作法，我們建議您這麼做之前部署 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="6ae9c-106">If you have not implemented these practices, we recommend that you do so before deploying Lync Server 2013.</span></span>

<span data-ttu-id="6ae9c-107">若要協助防止意外或故意傷害造成停機，Lync Server 2013 部署中的伺服器，請採取下列預防措施：</span><span class="sxs-lookup"><span data-stu-id="6ae9c-107">To help protect the servers in your Lync Server 2013 deployment from accidental or purposeful harm that might result in downtime, take the following precautions:</span></span>

  - <span data-ttu-id="6ae9c-108">隨時注意為伺服器安裝最新的安全性更新。</span><span class="sxs-lookup"><span data-stu-id="6ae9c-108">Keep your servers up-to-date with security updates.</span></span> <span data-ttu-id="6ae9c-109">註冊「微軟資訊安全通知服務」，確保能立即收到任何 Microsoft 產品的資訊安全佈告欄通知。</span><span class="sxs-lookup"><span data-stu-id="6ae9c-109">Subscribing to the Microsoft Security Notification Service helps ensure that you receive immediate notification of security bulletin releases for any Microsoft product.</span></span> <span data-ttu-id="6ae9c-110">若要訂閱，請移至 Microsoft 技術安全性通知網站在[https://go.microsoft.com/fwlink/p/?LinkId=145202](https://go.microsoft.com/fwlink/p/?linkid=145202)。</span><span class="sxs-lookup"><span data-stu-id="6ae9c-110">To subscribe, go to the Microsoft Technical Security Notifications website at [https://go.microsoft.com/fwlink/p/?LinkId=145202](https://go.microsoft.com/fwlink/p/?linkid=145202).</span></span>

  - <span data-ttu-id="6ae9c-111">確認已正確設定所有的存取權限。</span><span class="sxs-lookup"><span data-stu-id="6ae9c-111">Ensure that access rights are set up correctly.</span></span>

  - <span data-ttu-id="6ae9c-p103">請將您的伺服器配置於可預防未經授權擅自存取的實體環境。請確認您的伺服器均已安裝適當的防毒軟體。隨時注意安裝最新的病毒碼檔案，保持防毒軟體處於最新狀態。建議您使用防毒應用程式的自動更新功能，來維持最新的病毒碼狀態。</span><span class="sxs-lookup"><span data-stu-id="6ae9c-p103">Keep your servers in a physical environment that prevents unauthorized access. Ensure that adequate antivirus software is installed on all your servers. Keep the software up-to-date with the latest virus signature files. Use the automatic update feature of your antivirus application to keep the virus signatures current.</span></span>

  - <span data-ttu-id="6ae9c-116">我們建議您停用不需要您安裝 Lync Server 2013 的電腦的 Windows Server 作業系統服務。</span><span class="sxs-lookup"><span data-stu-id="6ae9c-116">We recommend that you disable the Windows Server operating system services that are not required on the computers where you install Lync Server 2013.</span></span>

  - <span data-ttu-id="6ae9c-117">為作業系統與磁碟機 (其中資料是以完整磁碟區加密系統存放) 加密，除非您能保證對伺服器能擁有持續及完整的控制、實體隔離總數且能適當與安全地解除委任已取代或故障的磁碟機。</span><span class="sxs-lookup"><span data-stu-id="6ae9c-117">Encrypt operating systems and disk drives where data is stored with a full-volume encryption system, unless you can guarantee constant and complete control of the servers, total physical isolation, and proper and secure decommissioning of replaced or failed disk drives.</span></span>

  - <span data-ttu-id="6ae9c-118">停用伺服器的所有外部直接記憶體存取 (DMA) 連接埠，除非您能保證對伺服器的實體存取擁有嚴密的控制。</span><span class="sxs-lookup"><span data-stu-id="6ae9c-118">Disable all external Direct Memory Access (DMA) ports of the server, unless you can guarantee very tight control over the physical access to the servers.</span></span> <span data-ttu-id="6ae9c-119">DMA 形式的攻擊通常非常容易啟動，這些攻擊可能會導致高度機密的資訊洩漏，例如私人加密金鑰等。</span><span class="sxs-lookup"><span data-stu-id="6ae9c-119">DMA-based attacks, which can be initiated fairly easily, could expose very sensitive information, such as private encryption keys.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

