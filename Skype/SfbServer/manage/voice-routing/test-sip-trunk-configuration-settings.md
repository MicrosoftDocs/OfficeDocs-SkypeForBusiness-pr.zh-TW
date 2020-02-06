---
title: 在商務用 Skype Server 中測試 SIP 幹線設定設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'SIP 幹線設定設定會定義在服務提供者上，exchange 中繼伺服器與公用交換式電話網絡（PSTN）閘道、IP 公用分支 exchange （PBX）或會話邊界控制器（SBC）之間的關聯性與能力。 '
ms.openlocfilehash: 911947b33f0e609b4dd532ec5cc2c3d56a08618c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816933"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="b6ae7-103">在商務用 Skype Server 中測試 SIP 幹線設定設定</span><span class="sxs-lookup"><span data-stu-id="b6ae7-103">Test SIP trunk configuration settings in Skype for Business Server</span></span>

<span data-ttu-id="b6ae7-104">SIP 幹線設定設定會定義在服務提供者上，exchange 中繼伺服器與公用交換式電話網絡（PSTN）閘道、IP 公用分支 exchange （PBX）或會話邊界控制器（SBC）之間的關聯性與能力。</span><span class="sxs-lookup"><span data-stu-id="b6ae7-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span> <span data-ttu-id="b6ae7-105">這些設定會以指定的方式執行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b6ae7-105">These settings do such things as specify:</span></span>

- <span data-ttu-id="b6ae7-106">是否應該在 trunks 上啟用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="b6ae7-106">Whether media bypass should be enabled on the trunks.</span></span>
- <span data-ttu-id="b6ae7-107">傳送即時傳輸控制通訊協定（RTCP）資料包的條件。</span><span class="sxs-lookup"><span data-stu-id="b6ae7-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>
- <span data-ttu-id="b6ae7-108">每個幹線是否都需要安全的即時通訊協定（SRTP）加密。</span><span class="sxs-lookup"><span data-stu-id="b6ae7-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="b6ae7-109">當您安裝商務用 Skype Server 時，系統會為您建立一個全域 SIP 中繼設定。</span><span class="sxs-lookup"><span data-stu-id="b6ae7-109">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="b6ae7-110">此外，管理員可以在網站範圍或服務範圍（僅限 PSTN 閘道服務）上建立自訂設定集合。</span><span class="sxs-lookup"><span data-stu-id="b6ae7-110">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span> <span data-ttu-id="b6ae7-111">系統管理員也可以使用[new-cstrunkconfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsTrunkConfiguration) Cmdlet 來驗證主幹能將使用者撥出的號碼轉換成可由閘道處理的數位。</span><span class="sxs-lookup"><span data-stu-id="b6ae7-111">Administrators can also use the [Test-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsTrunkConfiguration) cmdlet to verify that a trunk can convert a number as dialed by a user to a number that can be handled by the gateway.</span></span>

<span data-ttu-id="b6ae7-112">只能使用 Windows PowerShell 和 New-cstrunkconfiguration Cmdlet 來測試幹線設定設定。</span><span class="sxs-lookup"><span data-stu-id="b6ae7-112">Trunk configuration settings can only be tested by using Windows PowerShell and the Test-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="b6ae7-113">您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b6ae7-113">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

<span data-ttu-id="b6ae7-114">**測試 SIP 幹線設定設定**</span><span class="sxs-lookup"><span data-stu-id="b6ae7-114">**To test SIP trunk configuration settings**</span></span>

<span data-ttu-id="b6ae7-115">這個命令會驗證雷德蒙網站的幹線設定設定可以正確地轉換撥打的號碼4255551212。</span><span class="sxs-lookup"><span data-stu-id="b6ae7-115">This command verifies that the trunk configuration settings for the Redmond site can correctly convert the dialed number 4255551212.</span></span>

```PowerShell
$trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
```
