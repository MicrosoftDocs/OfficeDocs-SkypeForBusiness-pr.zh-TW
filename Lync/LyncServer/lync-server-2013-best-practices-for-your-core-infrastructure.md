---
title: Lync Server 2013：適用于核心基礎結構的最佳做法
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Best practices for your core infrastructure in Lync Server 2013
ms:assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518328(v=OCS.15)
ms:contentKeyID: 61071242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bfb6e12f6f2c6d66a0d4f5fed17bc01dc250db5e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976716"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-your-core-infrastructure-in-lync-server-2013"></a><span data-ttu-id="536a4-102">Lync Server 2013 中核心基礎結構的最佳做法</span><span class="sxs-lookup"><span data-stu-id="536a4-102">Best practices for your core infrastructure in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="536a4-103">_**主題上次修改日期：** 2014-01-27_</span><span class="sxs-lookup"><span data-stu-id="536a4-103">_**Topic Last Modified:** 2014-01-27_</span></span>

<span data-ttu-id="536a4-104">您可能已經採取步驟，在您的系統中設計容錯能力，例如確保硬體冗余、防範電源損失、例行安裝安全更新及防病毒措施，以及監視伺服器活動。</span><span class="sxs-lookup"><span data-stu-id="536a4-104">You have probably already taken steps to design fault tolerance in your system, using practices such as ensuring hardware redundancy, guarding against power loss, routinely installing security updates and antivirus measures, and Monitoring Server activity.</span></span> <span data-ttu-id="536a4-105">這些做法不僅能獲益您的 Microsoft Lync Server 2013 基礎結構，還能受益于整個網路。</span><span class="sxs-lookup"><span data-stu-id="536a4-105">These practices benefit not only your Microsoft Lync Server 2013 infrastructure, but also your entire network.</span></span> <span data-ttu-id="536a4-106">如果您尚未實現這些做法，建議您在部署 Lync Server 2013 之前先執行此動作。</span><span class="sxs-lookup"><span data-stu-id="536a4-106">If you have not implemented these practices, we recommend that you do so before deploying Lync Server 2013.</span></span>

<span data-ttu-id="536a4-107">若要協助保護 Lync Server 2013 部署中的伺服器不受意外或 purposeful 損害，可能會導致宕機，請採取下列預防措施：</span><span class="sxs-lookup"><span data-stu-id="536a4-107">To help protect the servers in your Lync Server 2013 deployment from accidental or purposeful harm that might result in downtime, take the following precautions:</span></span>

  - <span data-ttu-id="536a4-108">使用安全性更新讓伺服器保持在最新狀態。</span><span class="sxs-lookup"><span data-stu-id="536a4-108">Keep your servers up-to-date with security updates.</span></span> <span data-ttu-id="536a4-109">訂閱 Microsoft Security Notification 服務可協助確保您立即收到任何 Microsoft 產品的安全公告版本通知。</span><span class="sxs-lookup"><span data-stu-id="536a4-109">Subscribing to the Microsoft Security Notification Service helps ensure that you receive immediate notification of security bulletin releases for any Microsoft product.</span></span> <span data-ttu-id="536a4-110">若要訂閱，請移至 Microsoft 技術安全性通知網站[http://go.microsoft.com/fwlink/p/?LinkId=145202](http://go.microsoft.com/fwlink/p/?linkid=145202)：。</span><span class="sxs-lookup"><span data-stu-id="536a4-110">To subscribe, go to the Microsoft Technical Security Notifications website at [http://go.microsoft.com/fwlink/p/?LinkId=145202](http://go.microsoft.com/fwlink/p/?linkid=145202).</span></span>

  - <span data-ttu-id="536a4-111">確定正確設定存取權限。</span><span class="sxs-lookup"><span data-stu-id="536a4-111">Ensure that access rights are set up correctly.</span></span>

  - <span data-ttu-id="536a4-112">讓您的伺服器保持在可避免未經授權存取的實體環境中。</span><span class="sxs-lookup"><span data-stu-id="536a4-112">Keep your servers in a physical environment that prevents unauthorized access.</span></span> <span data-ttu-id="536a4-113">確保您的所有伺服器都安裝了適當的防毒軟體。</span><span class="sxs-lookup"><span data-stu-id="536a4-113">Ensure that adequate antivirus software is installed on all your servers.</span></span> <span data-ttu-id="536a4-114">使用最新的病毒簽名檔案，讓軟體保持在最新狀態。</span><span class="sxs-lookup"><span data-stu-id="536a4-114">Keep the software up-to-date with the latest virus signature files.</span></span> <span data-ttu-id="536a4-115">使用防病毒應用程式的自動更新功能，將病毒簽名保持在最新狀態。</span><span class="sxs-lookup"><span data-stu-id="536a4-115">Use the automatic update feature of your antivirus application to keep the virus signatures current.</span></span>

  - <span data-ttu-id="536a4-116">我們建議您停用安裝 Lync Server 2013 之電腦上不需要的 Windows Server 作業系統服務。</span><span class="sxs-lookup"><span data-stu-id="536a4-116">We recommend that you disable the Windows Server operating system services that are not required on the computers where you install Lync Server 2013.</span></span>

  - <span data-ttu-id="536a4-117">在儲存資料時使用完整容量加密系統來加密作業系統與磁片磁碟機，除非您能保證對伺服器的持續及完整控制、總物理隔離性，以及適當且安全地解除取代或失敗的磁片促進.</span><span class="sxs-lookup"><span data-stu-id="536a4-117">Encrypt operating systems and disk drives where data is stored with a full-volume encryption system, unless you can guarantee constant and complete control of the servers, total physical isolation, and proper and secure decommissioning of replaced or failed disk drives.</span></span>

  - <span data-ttu-id="536a4-118">停用伺服器的所有外部直接記憶體存取（DMA）埠，除非您能保證嚴格控制伺服器的物理存取權。</span><span class="sxs-lookup"><span data-stu-id="536a4-118">Disable all external Direct Memory Access (DMA) ports of the server, unless you can guarantee very tight control over the physical access to the servers.</span></span> <span data-ttu-id="536a4-119">DMA （可以相當輕鬆地啟動）的攻擊會公開非常敏感的資訊，例如私人加密金鑰。</span><span class="sxs-lookup"><span data-stu-id="536a4-119">DMA-based attacks, which can be initiated fairly easily, could expose very sensitive information, such as private encryption keys.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

