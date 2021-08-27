---
title: 查看網路介面資訊
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 您可以使用 Windows PowerShell 和 Get-CsNetworkInterface Cmdlet 來查看網路介面資訊。 您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端工作階段執行此 Cmdlet。
ms.openlocfilehash: 64e22ef14260ebadbbbe05ac1c7eff8cdf0b2ff1
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58585047"
---
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a>在商務用 Skype Server 中查看網路介面資訊

您可以使用 Windows PowerShell 和 **Get-CsNetworkInterface** Cmdlet 來查看網路介面資訊。 您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端工作階段執行此 Cmdlet。 

## <a name="to-view-network-interface-information"></a>若要查看網路介面資訊

  - 若要查看網路介面資訊，請在商務用 Skype Server 管理命令介面中輸入下列命令，然後按 enter：
    
        Get-CsNetworkInterface
    
    此命令會針對每個網路介面傳回類似下列的資訊：
    
        Identity              : dc.vdomain.com/Primary/1
        ComputerFqdn          : dc.vdomain.com
        IPAddress             : 0.0.0.0
        IPv6Address           :
        Interface             : Primary
        InterfaceNumber       : 1
        ConfiguredFqdn        :
        ConfiguredIPAddress   :
        ConfiguredIPv6Address :
    
    如需詳細資訊，請參閱 [Get-CsNetworkInterface](/powershell/module/skype/Get-CsNetworkInterface)。