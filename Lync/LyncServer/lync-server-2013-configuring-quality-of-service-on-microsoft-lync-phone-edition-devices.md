---
title: 在 Microsoft Lync Phone Edition 裝置上設定服務品質
description: 在 Microsoft Lync Phone Edition 裝置上設定服務品質。
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
ms.openlocfilehash: c0d1e4f10c6b4a550f5da25f8bd2e9fe97606255
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547939"
---
# <a name="configuring-quality-of-service-on-microsoft-lync-phone-edition-devices-in-lync-server-2013"></a>在 Lync Server 2013 中設定 Microsoft Lync Phone Edition 裝置上的服務品質

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

雖然服務品質 (QoS 不會為 Iphone 等裝置啟用) ，但預設為執行 Lync Phone Edition 的裝置啟用 QoS。  (這些裝置通常稱為 UC 或整合通訊電話。 ) 若要確認這一點，請從 Lync Server 管理命令介面中執行下列 Windows PowerShell 命令：

    Get-CsUCPhoneConfiguration

如果您未對 UC 電話設定設定進行任何變更，就會得到如下所示的資訊：

    Identity             : Global
    CalendarPollInterval : 00:03:00
    EnforcePhoneLock     : True
    PhoneLockTimeout     : 00:10:00
    MinPhonePinLength    : 6
    SIPSecurityMode      : High
    VoiceDiffServTag     : 40
    Voice8021p           : 0
    LoggingLevel         : Off

出於服務品質目的，只有其中一項屬性為相關事項： VoiceDiffServTag。 VoiceDiffServTag 代表指派給 Lync Phone Edition 裝置之語音流量 emanating 的 DSCP 值。

<div>


> [!NOTE]
> Lync Server 2013 中已不再支援 Voice8021p 參數。 參數仍然有效，可與 Microsoft Lync Server 2010 保持回溯相容性;不過，它不會影響 Lync Server 2013 使用的裝置。



</div>

在大部分的網路中，使用 VoiceDiffServTag 40 來標示 Lync Phone Edition 的資料包不會造成任何問題。 不過，40不是一般用於音訊流量的值;相反地，音訊流量幾乎都是以 DSCP 碼46標示。 為了維持整個網路的一致性，您可能想要將 UC 電話的 VoiceDiffServTag 屬性變更為46。

若要這麼做，您可以使用 [Windows PowerShell] 或 [Lync Server] 控制台。 若要使用 Windows PowerShell 來修改 VoiceDiffServTag 值，請在 Lync Server 管理命令介面中執行下列命令：

    Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

上述命令會修改 UC 電話設定的全域集合。 不過，請注意，也可以將 UC 電話設定指派給網站範圍。 若要修改網站範圍的 UC 電話設定設定，您必須指定網站身分識別。 例如：

    Set-CsUCPhoneConfiguration -Identity "site:Redmond" -VoiceDiffServTag 46

您也可以使用下列命令同時修改所有的 UC 電話設定：

    Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

如果您想要使用 Lync Server 控制台進行此變更，請啟動 [控制台]，然後完成下列程式：

1.  按一下 [ **用戶端** ]，然後按一下 [ **裝置**設定]。

2.  在 [ **裝置** 設定] 索引標籤上，按兩下您要修改的設定集合 (例如「 **全域**) 」。

3.  在 [ **編輯裝置** 設定] 對話方塊中，將 [ **語音服務品質 (QoS) ** ] 方塊的值設為 **46** ，然後按一下 [ **認可**]。

如果您有多個集合，則每個 UC 電話設定集合都需要重複此程式。 Lync Server 控制台不會允許您同時修改多個設定集合。

如果您有不是以 Windows 作業系統為基礎的裝置 (例如組織中的 Iphone) ，這些裝置將不會受到變更 VoiceDiffServTag 設定的影響。 如果您想要在這些裝置上變更 DSCP 值，您將需要參照每種裝置類型的管理手冊。

</div>

<span> </span>

</div>

</div>

</div>

