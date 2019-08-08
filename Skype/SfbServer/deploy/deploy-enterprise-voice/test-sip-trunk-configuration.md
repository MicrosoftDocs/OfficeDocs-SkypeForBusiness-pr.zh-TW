---
title: 在商務用 Skype Server 中測試 SIP 幹線設定設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
description: '摘要: 瞭解如何使用商務用 Skype Server Management Shell 來測試 SIP 幹線設定設定。'
ms.openlocfilehash: 1ef034f0b1de187e472fc3049573e9453e5a9505
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240304"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="38bc2-103">在商務用 Skype Server 中測試 SIP 幹線設定設定</span><span class="sxs-lookup"><span data-stu-id="38bc2-103">Test SIP trunk configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="38bc2-104">**摘要:** 瞭解如何使用商務用 Skype Server Management Shell 來測試 SIP 幹線設定設定。</span><span class="sxs-lookup"><span data-stu-id="38bc2-104">**Summary:** Learn how to test SIP trunk configuration settings by using the Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="38bc2-105">SIP 幹線設定設定會定義在服務提供者上, exchange 中繼伺服器與公用交換式電話網絡 (PSTN) 閘道、IP 公用分支 eXchange (PBX) 或會話邊界控制器 (SBC) 之間的關聯性與能力。</span><span class="sxs-lookup"><span data-stu-id="38bc2-105">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the Public Switched Telephone Network (PSTN) gateway, an IP-Public Branch eXchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span> <span data-ttu-id="38bc2-106">這些設定會以指定的方式執行以下操作:</span><span class="sxs-lookup"><span data-stu-id="38bc2-106">These settings do such things as specify:</span></span>
  
- <span data-ttu-id="38bc2-107">是否應該在 trunks 上啟用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="38bc2-107">Whether media bypass should be enabled on the trunks.</span></span>
    
- <span data-ttu-id="38bc2-108">傳送即時傳輸控制通訊協定 (RTCP) 資料包的條件。</span><span class="sxs-lookup"><span data-stu-id="38bc2-108">The conditions under which Realtime Transport Control Protocol (RTCP) packets are sent.</span></span>
    
- <span data-ttu-id="38bc2-109">每個幹線是否都需要安全的即時傳輸通訊協定 (SRTP) 加密。</span><span class="sxs-lookup"><span data-stu-id="38bc2-109">Whether or not Secure Realtime Transport Protocol (SRTP) encryption is required on each trunk.</span></span>
    
<span data-ttu-id="38bc2-110">當您安裝商務用 Skype Server 時, 系統會為您建立一個全域 SIP 中繼設定。</span><span class="sxs-lookup"><span data-stu-id="38bc2-110">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="38bc2-111">此外, 管理員可以在網站範圍或服務範圍 (僅限 PSTN 閘道服務) 上建立自訂設定集合。</span><span class="sxs-lookup"><span data-stu-id="38bc2-111">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span> <span data-ttu-id="38bc2-112">系統管理員也可以使用 New-cstrunkconfiguration Cmdlet 來驗證主幹能將使用者撥出的號碼轉換成可由閘道處理的數位。</span><span class="sxs-lookup"><span data-stu-id="38bc2-112">Administrators can also use the Test-CsTrunkConfiguration cmdlet to verify that a trunk can convert a number as dialed by a user to a number that can be handled by the gateway.</span></span>
  
<span data-ttu-id="38bc2-113">只能使用 Windows PowerShell 和[new-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/test-cstrunkconfiguration?view=skype-ps) Cmdlet 來測試幹線設定設定。</span><span class="sxs-lookup"><span data-stu-id="38bc2-113">Trunk configuration settings can only be tested by using Windows PowerShell and the [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/test-cstrunkconfiguration?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="38bc2-114">這個 Cmdlet 可以從商務用 Skype Server Management 命令介面或從商務用 Skype Server Management Shell 的遠端會話執行。</span><span class="sxs-lookup"><span data-stu-id="38bc2-114">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Skype for Business Server Management Shell.</span></span>
  
### <a name="to-test-sip-trunk-configuration-settings"></a><span data-ttu-id="38bc2-115">測試 SIP 幹線設定設定</span><span class="sxs-lookup"><span data-stu-id="38bc2-115">To test SIP trunk configuration settings</span></span>

- <span data-ttu-id="38bc2-116">這個命令會驗證雷德蒙網站的幹線設定設定可以正確地轉換撥打的號碼4255551212。</span><span class="sxs-lookup"><span data-stu-id="38bc2-116">This command verifies that the trunk configuration settings for the Redmond site can correctly convert the dialed number 4255551212.</span></span>
    
  ```
  $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
  Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
  ```


