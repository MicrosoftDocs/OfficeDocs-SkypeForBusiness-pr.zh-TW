---
title: Microsoft Lync Phone Edition 裝置上設定服務品質
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Quality of Service on Microsoft Lync Phone Edition devices
ms:assetid: a6eb2620-a512-4ab6-bdfd-eb76be43bbfe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205137(v=OCS.15)
ms:contentKeyID: 48185004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e154df7c71b32e9f5f1c1440707511bc91c3117
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213109"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-quality-of-service-on-microsoft-lync-phone-edition-devices-in-lync-server-2013"></a>在 Lync Server 2013 的 Microsoft Lync Phone Edition 裝置上設定服務品質

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-11-01_

雖然例如 Iphone 裝置的預設不會啟用服務品質 (QoS)，執行 Lync Phone Edition 裝置的預設會啟用 QoS。 （在這些裝置是通常稱為 UC 或整合通訊的電話。）若要確認此，請執行 Lync Server 管理命令介面中的從下列 Windows PowerShell 命令：

    Get-CsUCPhoneConfiguration

如果您不具有 UC 電話組態設定進行任何變更然後您會得到如下所示的資訊：

    Identity             : Global
    CalendarPollInterval : 00:03:00
    EnforcePhoneLock     : True
    PhoneLockTimeout     : 00:10:00
    MinPhonePinLength    : 6
    SIPSecurityMode      : High
    VoiceDiffServTag     : 40
    Voice8021p           : 0
    LoggingLevel         : Off

以服務品質來說，只有其中一個這些屬性會感興趣的： VoiceDiffServTag。 VoiceDiffServTag 代表指派給 emanating 從 Lync Phone Edition 裝置的語音流量的 DSCP 值。

<div>


> [!NOTE]
> Lync Server 2013 中已不再支援 Voice8021p 參數。 參數是仍適用於與 Microsoft Lync Server 2010; 回溯相容性不過，它就與 Lync Server 2013 搭配使用的裝置上沒有作用。



</div>

在大部分的網路中，標示為 40 VoiceDiffServTag 與 Lync Phone Edition 封包應該不會造成任何問題。 不過，40 不是通常用於音訊流量; 值相反地，DSCP 程式碼 46 幾乎都已標示音訊的流量。 為了維持整個網路的一致性，您可能想要變更為 [46 UC 電話的 VoiceDiffServTag 屬性。

若要這樣做，您可以使用 Windows PowerShell 或 Lync Server Control Panel。 若要使用 Windows PowerShell 修改 VoiceDiffServTag 值，執行從 Lync Server 管理命令介面中的下列命令：

    Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

上述命令會修改全域 UC 電話組態設定的集合。 不過請注意，也可以將 UC 電話設定指派至網站範圍。 若要修改在網站範圍的 UC 電話組態設定，您必須指定身分識別的網站。 例如：

    Set-CsUCPhoneConfiguration -Identity "site:Redmond" -VoiceDiffServTag 46

您也可以使用下列命令同時修改所有 UC 電話組態設定：

    Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

如果您想要使用 Lync Server Control Panel 此變更，然後啟動 [控制台]，然後完成下列程序：

1.  按一下 [**用戶端**，然後按一下 [**裝置組態**。

2.  在 [**裝置組態**] 索引標籤中，按兩下您想要修改 （例如，**全域**） 設定的集合。

3.  在 [**編輯裝置設定**] 對話方塊中，將**語音服務品質 (QoS)** ] 方塊的值設定為 [ **46** ，然後按一下 [**認可]**。

如果您有多個您想要重複此程序，針對每個集合的 UC 電話設定的集合。 Lync Server 控制台不允許您同時修改多個設定集合。

如果您有不採用 Windows 作業系統 （例如 Iphone) 在組織中的裝置這些裝置不會受到變更 VoiceDiffServTag 設定的影響。 如果您想要變更這些裝置上的 DSCP 值必須為每個裝置類型參照的管理手冊。

</div>

<span> </span>

</div>

</div>

</div>

