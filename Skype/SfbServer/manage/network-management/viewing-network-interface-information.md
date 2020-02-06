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
# <a name="viewing-network-interface-information-in-skype-for-business-server"></a>在商務用 Skype Server 中查看網路介面資訊

您可以使用 Windows PowerShell 和**CsNetworkInterface** Cmdlet 來查看網路介面資訊。 您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。 

## <a name="to-view-network-interface-information"></a>若要查看網路介面資訊

  - 若要查看網路介面資訊，請在商務用 Skype Server Management Shell 中輸入下列命令，然後按 ENTER 鍵：
    
        Get-CsNetworkInterface
    
    這個命令會針對每個網路介面傳回類似下列的資訊：
    
        Identity              : dc.vdomain.com/Primary/1
        ComputerFqdn          : dc.vdomain.com
        IPAddress             : 0.0.0.0
        IPv6Address           :
        Interface             : Primary
        InterfaceNumber       : 1
        ConfiguredFqdn        :
        ConfiguredIPAddress   :
        ConfiguredIPv6Address :
    
    如需詳細資訊，請參閱[CsNetworkInterface](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface)。


