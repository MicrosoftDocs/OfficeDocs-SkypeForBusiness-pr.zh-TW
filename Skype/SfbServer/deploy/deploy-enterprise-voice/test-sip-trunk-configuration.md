---
title: 在商務用 Skype Server 中測試 SIP 主幹設定設定
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
description: 摘要：瞭解如何使用商務用 Skype Server 管理命令介面來測試 SIP 主幹設定設定。
ms.openlocfilehash: 6f569c7e397e7902cb347e13b4077acb5a9b34fb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103369"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="7ee9f-103">在商務用 Skype Server 中測試 SIP 主幹設定設定</span><span class="sxs-lookup"><span data-stu-id="7ee9f-103">Test SIP trunk configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="7ee9f-104">**摘要：** 瞭解如何使用商務用 Skype Server 管理命令介面來測試 SIP 主幹設定設定。</span><span class="sxs-lookup"><span data-stu-id="7ee9f-104">**Summary:** Learn how to test SIP trunk configuration settings by using the Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="7ee9f-105">SIP 主幹設定設定定義轉送伺服器和公用交換電話網路 (PSTN) 閘道、IP-Public 分支 eXchange (PBX) 或會話邊界控制器（在服務提供者上 (SBC) ）之間的關聯性和功能。</span><span class="sxs-lookup"><span data-stu-id="7ee9f-105">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the Public Switched Telephone Network (PSTN) gateway, an IP-Public Branch eXchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span> <span data-ttu-id="7ee9f-106">這些設定將指定下列項目：</span><span class="sxs-lookup"><span data-stu-id="7ee9f-106">These settings do such things as specify:</span></span>
  
- <span data-ttu-id="7ee9f-107">主幹是否啟用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="7ee9f-107">Whether media bypass should be enabled on the trunks.</span></span>
    
- <span data-ttu-id="7ee9f-108">在哪個條件下會傳送即時傳輸控制通訊協定 (RTCP) 封包。</span><span class="sxs-lookup"><span data-stu-id="7ee9f-108">The conditions under which Realtime Transport Control Protocol (RTCP) packets are sent.</span></span>
    
- <span data-ttu-id="7ee9f-109">在每個主幹上是否需要 (SRTP) 加密的安全即時傳輸通訊協定。</span><span class="sxs-lookup"><span data-stu-id="7ee9f-109">Whether or not Secure Realtime Transport Protocol (SRTP) encryption is required on each trunk.</span></span>
    
<span data-ttu-id="7ee9f-110">當您安裝商務用 Skype Server 時，系統會為您建立一個全域 SIP 主幹設定的集合。</span><span class="sxs-lookup"><span data-stu-id="7ee9f-110">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="7ee9f-111">此外，系統管理員可以在網站範圍或服務範圍 (僅限 PSTN 閘道服務) 建立自訂設定集合。</span><span class="sxs-lookup"><span data-stu-id="7ee9f-111">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span> <span data-ttu-id="7ee9f-112">管理員也可以使用 Test-CsTrunkConfiguration Cmdlet 來驗證主幹是否可將使用者所撥打的號碼轉換為閘道可以處理的號碼。</span><span class="sxs-lookup"><span data-stu-id="7ee9f-112">Administrators can also use the Test-CsTrunkConfiguration cmdlet to verify that a trunk can convert a number as dialed by a user to a number that can be handled by the gateway.</span></span>
  
<span data-ttu-id="7ee9f-113">您只能使用 Windows PowerShell 和 [Test-CsTrunkConfiguration](/powershell/module/skype/test-cstrunkconfiguration?view=skype-ps) Cmdlet 來測試主幹設定設定。</span><span class="sxs-lookup"><span data-stu-id="7ee9f-113">Trunk configuration settings can only be tested by using Windows PowerShell and the [Test-CsTrunkConfiguration](/powershell/module/skype/test-cstrunkconfiguration?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="7ee9f-114">您可以從商務用 Skype Server 管理命令介面或從商務用 Skype Server 管理命令介面的遠端會話執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7ee9f-114">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Skype for Business Server Management Shell.</span></span>
  
### <a name="to-test-sip-trunk-configuration-settings"></a><span data-ttu-id="7ee9f-115">測試 SIP 主幹設定設定</span><span class="sxs-lookup"><span data-stu-id="7ee9f-115">To test SIP trunk configuration settings</span></span>

- <span data-ttu-id="7ee9f-116">這個命令會驗證 Redmond 網站的主幹設定設定是否可以正確地轉換撥打的號碼4255551212。</span><span class="sxs-lookup"><span data-stu-id="7ee9f-116">This command verifies that the trunk configuration settings for the Redmond site can correctly convert the dialed number 4255551212.</span></span>
    
  ```powershell
  $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
  Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
  ```