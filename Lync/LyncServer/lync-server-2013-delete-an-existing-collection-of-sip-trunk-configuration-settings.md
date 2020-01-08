---
title: 刪除現有的 SIP 幹線配置設定集合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete an existing collection of SIP trunk configuration settings
ms:assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688024(v=OCS.15)
ms:contentKeyID: 49733614
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b896d53760184d15b02afed14b8a9c0d660f96b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981818"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-lync-server-2013"></a>刪除 Lync Server 2013 中現有的 SIP 幹線配置設定集合

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-22_

SIP 幹線設定設定會定義在服務提供者上，exchange 中繼伺服器與公用交換式電話網絡（PSTN）閘道、IP 公用分支 exchange （PBX）或會話邊界控制器（SBC）之間的關聯性與能力。 這些設定會以指定的方式執行以下操作：

  - 是否應該在 trunks 上啟用媒體旁路。

  - 傳送即時傳輸控制通訊協定（RTCP）資料包的條件。

  - 每個幹線是否都需要安全的即時通訊協定（SRTP）加密。

當您安裝 Microsoft Lync Server 2013 時，系統會為您建立一個全域 SIP 幹線配置設定。 這個全域設定集合無法刪除。 不過，您可以使用 Lync Server [控制台] 或 [[移除-new-cstrunkconfiguration](https://technet.microsoft.com/en-us/library/Gg425943(v=OCS.15)) ] Cmdlet，將全域集合中的屬性「重設」為預設值。 例如，如果您已將 Enable3pccRefer 屬性設為 True，當您重設全域集合時，Enable3pccRefer 屬性將會還原為預設值 False。

系統管理員也可以在網站範圍或服務範圍（針對個別 PSTN 閘道）建立自訂主幹設定設定。您可以移除這些自訂設定。 移除這些自訂設定時，請記住下列事項：

  - 如果您移除服務範圍設定，這些設定所管理的 SIP 幹線將由套用至其網站的設定來管理（如果存在的話）。 如果網站設定不存在，這些 trunks 就會受到中繼設定設定的全域集合的管理。

  - 如果您移除網站範圍的設定，由這些設定所管理的任何 SIP trunks 現在都將由「中繼設定」全域集合來管理。

<div>

## <a name="to-remove-trunk-configuration-settings-with-lync-server-control-panel"></a>使用 Lync Server 控制台移除主幹設定設定

1.  在 Lync Server [控制台] 中，按一下 [**語音路由**]，然後按一下 [**幹線**設定]。

2.  在 [**幹線**設定] 索引標籤上，選取要刪除的 SIP 中繼設定的集合，按一下 [**編輯**]，然後按一下 [**刪除**]。 若要在相同的作業中刪除多個集合，請按一下要刪除的第一個集合，然後按住 Ctrl 鍵並按一下您想要移除的任何其他集合。

3.  集合的**State**屬性會更新為**未提交**。 若要確認變更，並刪除收藏，請按一下 [**認可**]，然後按一下 [**全部確認**]。

4.  在 [**未提交的語音設定**] 對話方塊中，按一下 **[確定]**。

5.  在 [ **Microsoft Lync Server 2013 控制台**] 對話方塊中，按一下 **[確定]**。

6.  如果您改變主意，並決定不刪除收藏，請按一下 [**認可**]，然後按一下 [**取消所有未提交的變更**]。 當 [ **Microsoft Lync Server 2013 控制台**] 對話方塊出現時，請按一下 **[確定]**。

</div>

<div>

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 移除主幹設定設定

您可以使用 Windows PowerShell 與**Remove new-cstrunkconfiguration** Cmdlet 來刪除主幹設定設定。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 遠端會話中執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-remove-a-specified-collection-of-settings"></a>移除指定的設定集合

  - 下列命令會移除套用至雷德蒙網站的幹線設定設定：
    
        Remove-CsTrunkConfiguration -Identity site:Redmond

</div>

<div>

## <a name="to-remove-all-the-collections-applied-to-the-site-scope"></a>若要移除所有套用至網站範圍的集合

  - 這個命令會移除所有已套用至服務範圍的中繼設定設定：
    
        Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration

</div>

<div>

## <a name="to-remove-all-the-collections-where-media-bypass-is-enabled"></a>若要移除已啟用媒體旁路的所有集合

  - 下列命令會移除已啟用媒體略過的所有主幹設定設定：
    
        Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration

</div>

如需詳細資訊，請參閱[Remove new-cstrunkconfiguration](https://technet.microsoft.com/en-us/library/Gg425943(v=OCS.15)) Cmdlet 的說明主題。

</div>

</div>

<span> </span>

</div>

</div>

</div>

