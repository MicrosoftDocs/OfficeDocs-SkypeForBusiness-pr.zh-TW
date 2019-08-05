---
title: 查看網路介面資訊
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 您可以使用 Windows PowerShell 和 CsNetworkInterface Cmdlet 來查看網路介面資訊。 您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。
ms.openlocfilehash: ac0df8450b938a377e1325f9c3179b4650b31bdf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188524"
---
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a><span data-ttu-id="66239-104">在商務用 Skype Server 中查看網路介面資訊</span><span class="sxs-lookup"><span data-stu-id="66239-104">Viewing network interface information in Skype for Business Server</span></span>

<span data-ttu-id="66239-105">您可以使用 Windows PowerShell 和**CsNetworkInterface** Cmdlet 來查看網路介面資訊。</span><span class="sxs-lookup"><span data-stu-id="66239-105">You can view network interface information by using Windows PowerShell and the **Get-CsNetworkInterface** cmdlet.</span></span> <span data-ttu-id="66239-106">您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="66239-106">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-view-network-interface-information"></a><span data-ttu-id="66239-107">若要查看網路介面資訊</span><span class="sxs-lookup"><span data-stu-id="66239-107">To view network interface information</span></span>

  - <span data-ttu-id="66239-108">若要查看網路介面資訊, 請在商務用 Skype Server Management Shell 中輸入下列命令, 然後按 ENTER 鍵:</span><span class="sxs-lookup"><span data-stu-id="66239-108">To view network interface information, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkInterface
    
    <span data-ttu-id="66239-109">這個命令會針對每個網路介面傳回類似下列的資訊:</span><span class="sxs-lookup"><span data-stu-id="66239-109">This command returns information similar to the following for each network interface:</span></span>
    
        Identity              : dc.vdomain.com/Primary/1
        ComputerFqdn          : dc.vdomain.com
        IPAddress             : 0.0.0.0
        IPv6Address           :
        Interface             : Primary
        InterfaceNumber       : 1
        ConfiguredFqdn        :
        ConfiguredIPAddress   :
        ConfiguredIPv6Address :
    
    <span data-ttu-id="66239-110">如需詳細資訊, 請參閱[CsNetworkInterface](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface)。</span><span class="sxs-lookup"><span data-stu-id="66239-110">For details, see [Get-CsNetworkInterface](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface).</span></span>


