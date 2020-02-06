---
title: 查看網路介面資訊
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
description: 您可以使用 Windows PowerShell 和 CsNetworkInterface Cmdlet 來查看網路介面資訊。 您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。
ms.openlocfilehash: d4443f7ec10a0f56cc82ab495d88518f3f3aa17d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817349"
---
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a><span data-ttu-id="86ca2-104">在商務用 Skype Server 中查看網路介面資訊</span><span class="sxs-lookup"><span data-stu-id="86ca2-104">Viewing network interface information in Skype for Business Server</span></span>

<span data-ttu-id="86ca2-105">您可以使用 Windows PowerShell 和**CsNetworkInterface** Cmdlet 來查看網路介面資訊。</span><span class="sxs-lookup"><span data-stu-id="86ca2-105">You can view network interface information by using Windows PowerShell and the **Get-CsNetworkInterface** cmdlet.</span></span> <span data-ttu-id="86ca2-106">您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="86ca2-106">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-view-network-interface-information"></a><span data-ttu-id="86ca2-107">若要查看網路介面資訊</span><span class="sxs-lookup"><span data-stu-id="86ca2-107">To view network interface information</span></span>

  - <span data-ttu-id="86ca2-108">若要查看網路介面資訊，請在商務用 Skype Server Management Shell 中輸入下列命令，然後按 ENTER 鍵：</span><span class="sxs-lookup"><span data-stu-id="86ca2-108">To view network interface information, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkInterface
    
    <span data-ttu-id="86ca2-109">這個命令會針對每個網路介面傳回類似下列的資訊：</span><span class="sxs-lookup"><span data-stu-id="86ca2-109">This command returns information similar to the following for each network interface:</span></span>
    
        Identity              : dc.vdomain.com/Primary/1
        ComputerFqdn          : dc.vdomain.com
        IPAddress             : 0.0.0.0
        IPv6Address           :
        Interface             : Primary
        InterfaceNumber       : 1
        ConfiguredFqdn        :
        ConfiguredIPAddress   :
        ConfiguredIPv6Address :
    
    <span data-ttu-id="86ca2-110">如需詳細資訊，請參閱[CsNetworkInterface](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface)。</span><span class="sxs-lookup"><span data-stu-id="86ca2-110">For details, see [Get-CsNetworkInterface](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface).</span></span>


