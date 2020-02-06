---
title: 在商務用 Skype Server 中查看個別 SIP trunks 的相關資訊
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
description: 在商務用 Skype Server 中，可以將多個 trunks 指派給單一 PSTN 閘道;這表示閘道與 trunks 不是一個，且系統管理員必須使用 CsTrunk Cmdlet 來查看個別 SIP 幹線的相關資訊。
ms.openlocfilehash: d7db7eebfc409b0f79bd562606368d434ba47f0c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816922"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a>在商務用 Skype Server 中查看個別 SIP trunks 的相關資訊

在商務用 Skype Server 中，可以將多個 trunks 指派給單一 PSTN 閘道;這表示閘道與 trunks 不是一個且相同，且系統管理員必須使用[CsTrunk](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunk) Cmdlet 來查看個別 SIP 幹線的相關資訊。

CsTrunk Cmdlet 可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行。

**若要查看所有 SIP trunks 的相關資訊**

下列命令會傳回貴組織中使用的所有 SIP trunks 資訊：

`Get-CsTrunk`

**若要查看特定 SIP 主幹的資訊**

這個命令只會傳回具有身分識別 PstnGateway 的 SIP 幹線資訊：192.168.0.240：

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

**查看指派給某個池之所有 SIP Trunks 的相關資訊**

在這個範例中，會針對指派給 pool atl-cs-001.litwareinc.com 的所有 SIP trunks 傳回信息：

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`
