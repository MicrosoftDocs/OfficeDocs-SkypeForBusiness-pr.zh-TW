---
title: Lync Server 2013：核心基礎結構的最佳作法
description: Lync Server 2013：核心基礎結構的最佳作法。
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
ms.openlocfilehash: d0ea7cb9c7685a3b6f7c04146ec5631bbac10fe6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552189"
---
# <a name="best-practices-for-your-core-infrastructure-in-lync-server-2013"></a><span data-ttu-id="92fa9-103">Lync Server 2013 中核心基礎結構的最佳作法</span><span class="sxs-lookup"><span data-stu-id="92fa9-103">Best practices for your core infrastructure in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="92fa9-104">_**主題上次修改日期：** 2014-01-27_</span><span class="sxs-lookup"><span data-stu-id="92fa9-104">_**Topic Last Modified:** 2014-01-27_</span></span>

<span data-ttu-id="92fa9-105">您可能已經採取一些步驟，包括透過確保硬體備份、避免電源中斷、例行性地安裝安全性更新與防毒措施，以及監控伺服器活動等作法，為您的系統設計容錯機制。</span><span class="sxs-lookup"><span data-stu-id="92fa9-105">You have probably already taken steps to design fault tolerance in your system, using practices such as ensuring hardware redundancy, guarding against power loss, routinely installing security updates and antivirus measures, and Monitoring Server activity.</span></span> <span data-ttu-id="92fa9-106">這些做法不僅受益于您的 Microsoft Lync Server 2013 基礎結構，還受益于整個網路。</span><span class="sxs-lookup"><span data-stu-id="92fa9-106">These practices benefit not only your Microsoft Lync Server 2013 infrastructure, but also your entire network.</span></span> <span data-ttu-id="92fa9-107">如果您尚未執行這些做法，建議您在部署 Lync Server 2013 之前先執行此動作。</span><span class="sxs-lookup"><span data-stu-id="92fa9-107">If you have not implemented these practices, we recommend that you do so before deploying Lync Server 2013.</span></span>

<span data-ttu-id="92fa9-108">為了協助保護 Lync Server 2013 部署中的伺服器，避免意外或惡意可能會造成停機的損害，請採取下列預防措施：</span><span class="sxs-lookup"><span data-stu-id="92fa9-108">To help protect the servers in your Lync Server 2013 deployment from accidental or purposeful harm that might result in downtime, take the following precautions:</span></span>

  - <span data-ttu-id="92fa9-109">隨時注意為伺服器安裝最新的安全性更新。</span><span class="sxs-lookup"><span data-stu-id="92fa9-109">Keep your servers up-to-date with security updates.</span></span> <span data-ttu-id="92fa9-110">註冊「微軟資訊安全通知服務」，確保能立即收到任何 Microsoft 產品的資訊安全佈告欄通知。</span><span class="sxs-lookup"><span data-stu-id="92fa9-110">Subscribing to the Microsoft Security Notification Service helps ensure that you receive immediate notification of security bulletin releases for any Microsoft product.</span></span> <span data-ttu-id="92fa9-111">若要訂閱，請前往中的 Microsoft 技術安全性通知網站 [https://go.microsoft.com/fwlink/p/?LinkId=145202](https://go.microsoft.com/fwlink/p/?linkid=145202) 。</span><span class="sxs-lookup"><span data-stu-id="92fa9-111">To subscribe, go to the Microsoft Technical Security Notifications website at [https://go.microsoft.com/fwlink/p/?LinkId=145202](https://go.microsoft.com/fwlink/p/?linkid=145202).</span></span>

  - <span data-ttu-id="92fa9-112">確認已正確設定所有的存取權限。</span><span class="sxs-lookup"><span data-stu-id="92fa9-112">Ensure that access rights are set up correctly.</span></span>

  - <span data-ttu-id="92fa9-p103">請將您的伺服器配置於可預防未經授權擅自存取的實體環境。請確認您的伺服器均已安裝適當的防毒軟體。隨時注意安裝最新的病毒碼檔案，保持防毒軟體處於最新狀態。建議您使用防毒應用程式的自動更新功能，來維持最新的病毒碼狀態。</span><span class="sxs-lookup"><span data-stu-id="92fa9-p103">Keep your servers in a physical environment that prevents unauthorized access. Ensure that adequate antivirus software is installed on all your servers. Keep the software up-to-date with the latest virus signature files. Use the automatic update feature of your antivirus application to keep the virus signatures current.</span></span>

  - <span data-ttu-id="92fa9-117">建議您停用安裝 Lync Server 2013 之電腦不需要的 Windows Server 作業系統服務。</span><span class="sxs-lookup"><span data-stu-id="92fa9-117">We recommend that you disable the Windows Server operating system services that are not required on the computers where you install Lync Server 2013.</span></span>

  - <span data-ttu-id="92fa9-118">為作業系統與磁碟機 (其中資料是以完整磁碟區加密系統存放) 加密，除非您能保證對伺服器能擁有持續及完整的控制、實體隔離總數且能適當與安全地解除委任已取代或故障的磁碟機。</span><span class="sxs-lookup"><span data-stu-id="92fa9-118">Encrypt operating systems and disk drives where data is stored with a full-volume encryption system, unless you can guarantee constant and complete control of the servers, total physical isolation, and proper and secure decommissioning of replaced or failed disk drives.</span></span>

  - <span data-ttu-id="92fa9-119">停用伺服器的所有外部直接記憶體存取 (DMA) 連接埠，除非您能保證對伺服器的實體存取擁有嚴密的控制。</span><span class="sxs-lookup"><span data-stu-id="92fa9-119">Disable all external Direct Memory Access (DMA) ports of the server, unless you can guarantee very tight control over the physical access to the servers.</span></span> <span data-ttu-id="92fa9-120">DMA 形式的攻擊通常非常容易啟動，這些攻擊可能會導致高度機密的資訊洩漏，例如私人加密金鑰等。</span><span class="sxs-lookup"><span data-stu-id="92fa9-120">DMA-based attacks, which can be initiated fairly easily, could expose very sensitive information, such as private encryption keys.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

