---
title: 在 Microsoft Lync Phone Edition 裝置上設定品質服務
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Quality of Service on Microsoft Lync Phone Edition devices
ms:assetid: a6eb2620-a512-4ab6-bdfd-eb76be43bbfe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205137(v=OCS.15)
ms:contentKeyID: 48185004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a9f7f96e90aa07da193f9ffb714fc3437ba46cd8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974039"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-quality-of-service-on-microsoft-lync-phone-edition-devices-in-lync-server-2013"></a>在 Lync Server 2013 中設定 Microsoft Lync Phone Edition 裝置上的服務品質

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

雖然預設不會針對裝置（例如 Iphone）啟用服務品質（QoS），但在執行 Lync Phone Edition 的裝置上預設會啟用 QoS。 （這些裝置通常稱為 [UC] 或 [整合通訊電話]）。若要驗證這一點，請從 Lync Server Management Shell 中執行下列 Windows PowerShell 命令：

    Get-CsUCPhoneConfiguration

如果您未對 UC 手機設定設定進行任何變更，則會傳回如下所示的資訊：

    Identity             : Global
    CalendarPollInterval : 00:03:00
    EnforcePhoneLock     : True
    PhoneLockTimeout     : 00:10:00
    MinPhonePinLength    : 6
    SIPSecurityMode      : High
    VoiceDiffServTag     : 40
    Voice8021p           : 0
    LoggingLevel         : Off

針對服務品質而言，只有下列其中一個屬性是重要的： VoiceDiffServTag。 VoiceDiffServTag 代表指派給 Lync Phone Edition 裝置的語音流量 emanating 的 DSCP 值。

<div>


> [!NOTE]
> Lync Server 2013 不再支援 Voice8021p 參數。 這個參數仍然有效，可讓您與 Microsoft Lync Server 2010 保持向後相容;不過，它不會影響 Lync Server 2013 使用的裝置。



</div>

在大部分的網路中，使用 VoiceDiffServTag 40 來標示 Lync Phone Edition 資料包不會造成任何問題。 不過，40不是通常用於音訊流量的值;相反地，音訊流量幾乎總是以 DSCP 代碼46標示。 為了維持整個網路的一致性，您可能會想要將 UC 手機的 VoiceDiffServTag 屬性變更為46。

若要這樣做，您可以使用 Windows PowerShell 或 Lync Server [控制台]。 若要使用 Windows PowerShell 來修改 VoiceDiffServTag 值，請在 Lync Server 管理命令介面中執行下列命令：

    Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

上述命令會修改 UC 手機設定的全域集合。 但請注意，UC 電話設定也可以指派給網站範圍。 若要在網站範圍修改 UC 手機設定，您必須指定網站身分識別。 例如：

    Set-CsUCPhoneConfiguration -Identity "site:Redmond" -VoiceDiffServTag 46

您也可以使用下列命令，同時修改所有的 UC 手機設定：

    Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

如果您想要使用 Lync Server [控制台] 進行這項變更，請啟動 [控制台]，然後完成下列程式：

1.  按一下 [**用戶端**]，然後按一下 [**裝置配置**]。

2.  在 [**裝置**設定] 索引標籤上，按兩下您要修改的設定集合（例如 [**全域**]）。

3.  在 [**編輯裝置**設定] 對話方塊中，將 [**語音服務品質（QoS）** ] 方塊的值設定為**46** ，然後按一下 [Commit] （**提交**）。

如果您有多個集合，您將需要針對每個 UC 手機設定集合重複此程式。 Lync Server [控制台] 不會讓您同時修改多個設定集合。

如果您的裝置不是以 Windows 作業系統（例如 Iphone）為基礎，這些裝置將不會受到變更 VoiceDiffServTag 設定的影響。 如果您想要變更這些裝置上的 DSCP 值，您需要參照每個裝置類型的系統管理手冊。

</div>

<span> </span>

</div>

</div>

</div>

