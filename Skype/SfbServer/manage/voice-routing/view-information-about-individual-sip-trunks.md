---
title: 商務用 Skype Server-查看個別 SIP 主幹的相關資訊
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
description: 在商務用 Skype Server 中，可以將多個主幹指派給單一 PSTN 閘道。 閘道和主幹不是一個，而且必須使用 Get-CsTrunk Cmdlet 來查看個別 SIP 主幹的相關資訊。
---

# <a name="skype-for-business-server---view-information-about-individual-sip-trunks"></a>商務用 Skype Server-查看個別 SIP 主幹的相關資訊

在商務用 Skype Server 中，可以將多個主幹指派給單一 PSTN 閘道; 這表示閘道和主幹不是一或相同，而且系統管理員必須使用[Get-CsTrunk](/powershell/module/skype/Get-CsTrunk) Cmdlet 來查看個別 SIP 主幹的相關資訊。

Get-CsTrunk Cmdlet 既可以從商務用 Skype Server 管理命令介面，也可以從 Windows PowerShell 的遠端會話執行。

**若要查看所有 SIP 主幹的資訊**

下列命令會傳回組織中使用之所有 SIP 主幹的資訊：

`Get-CsTrunk`

**若要查看特定 SIP 主幹的資訊**

這個命令只會傳回身分識別 PstnGateway:192.168.0.240 的 SIP 主幹資訊：

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

**查看指派至集區之所有 SIP 主幹的資訊**

在此範例中，會傳回指派給集區 atl-cs-001.litwareinc.com 的所有 SIP 主幹的資訊：

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`
