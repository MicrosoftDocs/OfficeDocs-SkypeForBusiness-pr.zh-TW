---
title: 商務用 Skype Server 中的核心基礎結構最佳做法
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
description: 您可能已經採取步驟，在您的系統中設計容錯能力，例如確保硬體冗余、防範電源損失、例行安裝安全更新及防病毒措施，以及監視伺服器活動。 這些做法不僅能獲益您的商務用 Skype 伺服器基礎結構，還能受益于整個網路。 如果您尚未實現這些做法，建議您在部署商務用 Skype Server 之前先執行此動作。
ms.openlocfilehash: 62200fc1ac45e1d647761af24d176a00d18693e4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815681"
---
# <a name="best-practices-for-your-core-infrastructure-in-skype-for-business-server"></a><span data-ttu-id="93f28-105">商務用 Skype Server 中的核心基礎結構最佳做法</span><span class="sxs-lookup"><span data-stu-id="93f28-105">Best practices for your core infrastructure in Skype for Business Server</span></span>
 
<span data-ttu-id="93f28-106">您可能已經採取步驟，在您的系統中設計容錯能力，例如確保硬體冗余、防範電源損失、例行安裝安全更新及防病毒措施，以及監視伺服器活動。</span><span class="sxs-lookup"><span data-stu-id="93f28-106">You have probably already taken steps to design fault tolerance in your system, using practices such as ensuring hardware redundancy, guarding against power loss, routinely installing security updates and antivirus measures, and Monitoring Server activity.</span></span> <span data-ttu-id="93f28-107">這些做法不僅能獲益您的商務用 Skype 伺服器基礎結構，還能受益于整個網路。</span><span class="sxs-lookup"><span data-stu-id="93f28-107">These practices benefit not only your Skype for Business Server infrastructure, but also your entire network.</span></span> <span data-ttu-id="93f28-108">如果您尚未實現這些做法，建議您在部署商務用 Skype Server 之前先執行此動作。</span><span class="sxs-lookup"><span data-stu-id="93f28-108">If you have not implemented these practices, we recommend that you do so before deploying Skype for Business Server.</span></span>
  
<span data-ttu-id="93f28-109">若要協助保護商務用 Skype Server 部署中的伺服器不受意外或 purposeful 損害，可能會導致宕機，請採取下列預防措施：</span><span class="sxs-lookup"><span data-stu-id="93f28-109">To help protect the servers in your Skype for Business Server deployment from accidental or purposeful harm that might result in downtime, take the following precautions:</span></span>
  
- <span data-ttu-id="93f28-110">使用安全性更新讓伺服器保持在最新狀態。</span><span class="sxs-lookup"><span data-stu-id="93f28-110">Keep your servers up-to-date with security updates.</span></span> <span data-ttu-id="93f28-111">訂閱 Microsoft Security Notification 服務可協助確保您立即收到任何 Microsoft 產品的安全公告版本通知。</span><span class="sxs-lookup"><span data-stu-id="93f28-111">Subscribing to the Microsoft Security Notification Service helps ensure that you receive immediate notification of security bulletin releases for any Microsoft product.</span></span> <span data-ttu-id="93f28-112">若要訂閱，請移至[Microsoft 技術安全性通知網站](https://go.microsoft.com/fwlink/p/?LinkId=145202)。</span><span class="sxs-lookup"><span data-stu-id="93f28-112">To subscribe, go to the [Microsoft Technical Security Notifications website](https://go.microsoft.com/fwlink/p/?LinkId=145202).</span></span>
    
- <span data-ttu-id="93f28-113">確定正確設定存取權限。</span><span class="sxs-lookup"><span data-stu-id="93f28-113">Ensure that access rights are set up correctly.</span></span>
    
- <span data-ttu-id="93f28-114">讓您的伺服器保持在可避免未經授權存取的實體環境中。</span><span class="sxs-lookup"><span data-stu-id="93f28-114">Keep your servers in a physical environment that prevents unauthorized access.</span></span> <span data-ttu-id="93f28-115">確保您的所有伺服器都安裝了適當的防毒軟體。</span><span class="sxs-lookup"><span data-stu-id="93f28-115">Ensure that adequate antivirus software is installed on all your servers.</span></span> <span data-ttu-id="93f28-116">使用最新的病毒簽名檔案，讓軟體保持在最新狀態。</span><span class="sxs-lookup"><span data-stu-id="93f28-116">Keep the software up-to-date with the latest virus signature files.</span></span> <span data-ttu-id="93f28-117">使用防病毒應用程式的自動更新功能，將病毒簽名保持在最新狀態。</span><span class="sxs-lookup"><span data-stu-id="93f28-117">Use the automatic update feature of your antivirus application to keep the virus signatures current.</span></span>
    
- <span data-ttu-id="93f28-118">我們建議您停用您在安裝商務用 Skype Server 的電腦上不需要的 Windows Server 作業系統服務。</span><span class="sxs-lookup"><span data-stu-id="93f28-118">We recommend that you disable the Windows Server operating system services that are not required on the computers where you install Skype for Business Server.</span></span>
    
- <span data-ttu-id="93f28-119">在儲存資料時使用完整容量加密系統來加密作業系統與磁片磁碟機，除非您能保證對伺服器的持續及完整控制、總物理隔離性，以及適當且安全地解除取代或失敗的磁片促進.</span><span class="sxs-lookup"><span data-stu-id="93f28-119">Encrypt operating systems and disk drives where data is stored with a full-volume encryption system, unless you can guarantee constant and complete control of the servers, total physical isolation, and proper and secure decommissioning of replaced or failed disk drives.</span></span>
    
- <span data-ttu-id="93f28-120">停用伺服器的所有外部直接記憶體存取（DMA）埠，除非您能保證嚴格控制伺服器的物理存取權。</span><span class="sxs-lookup"><span data-stu-id="93f28-120">Disable all external Direct Memory Access (DMA) ports of the server, unless you can guarantee very tight control over the physical access to the servers.</span></span> <span data-ttu-id="93f28-121">DMA （可以相當輕鬆地啟動）的攻擊會公開非常敏感的資訊，例如私人加密金鑰。</span><span class="sxs-lookup"><span data-stu-id="93f28-121">DMA-based attacks, which can be initiated fairly easily, could expose very sensitive information, such as private encryption keys.</span></span>
    

