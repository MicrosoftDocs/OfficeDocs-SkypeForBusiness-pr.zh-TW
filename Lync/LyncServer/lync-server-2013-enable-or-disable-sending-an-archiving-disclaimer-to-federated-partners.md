---
title: 啟用或停用傳送封存免責聲明至同盟合作夥伴的功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable sending an Archiving disclaimer to federated partners
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48185391
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f53e03ebfdc24ff969ff44a9b39149456ab3f16
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736044"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-lync-server-2013"></a>在 Lync Server 2013 中啟用或停用傳送封存免責聲明至同盟合作夥伴的功能

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

在您部署您的 Edge 伺服器並為貴組織啟用同盟後，您應該已指定是否要將封存免責聲明自動傳送給聯盟夥伴。 如果您封存外部通訊，您應該啟用傳送封存免責聲明。 使用本主題中的程式來變更該設定。

<div>


> [!NOTE]
> 下列程式假設您已經為您的組織啟用同盟。 如需啟用同盟的詳細資料，請參閱在部署檔或操作檔中<A href="lync-server-2013-enable-or-disable-remote-user-access.md">啟用或停用 Lync Server 2013 中的遠端使用者存取</A>。



</div>

<div>

## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a>啟用或停用將封存免責聲明傳送給聯盟夥伴

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**外部使用者存取**]，然後按一下 [**存取邊緣**設定]。

4.  按一下 [**存取邊緣**設定] 索引標籤上的 [**全域**]，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。

5.  在 [**編輯存取邊緣**設定] 的 [**啟用與聯盟使用者的通訊**] 底下，選取或清除 [**將封存放棄免責聲明傳送給聯盟夥伴**] 核取方塊，以啟用或停用自動傳送封存免責聲明。

6.  按一下 [認可]****。

若要讓聯盟使用者在 Lync Server 2013 部署中與使用者共同作業，您必須至少已將一個外部存取原則設定為支援同盟使用者存取。 如需詳細資訊，請參閱在部署檔或作業檔中[管理 Lync Server 2013 中的 XMPP 聯盟合作夥伴](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)。 如需控制特定聯盟網域存取權的詳細資料，請參閱在部署檔或操作檔中[設定 Lync Server 2013 允許的外部網域支援](lync-server-2013-configure-support-for-allowed-external-domains.md)。

</div>

<div>

## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 來啟用或停用封存放棄免責聲明

您可以使用 Windows PowerShell 和 CsAccessEdgeConfiguration Cmdlet 來管理存檔免責聲明的使用。 這個 Cmdlet 可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-enable-the-archiving-disclaimer"></a>啟用封存放棄免責聲明

  - 若要啟用封存免責聲明，請將**EnableArchivingDisclaimer**屬性的值設定為 True （$True）：
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

</div>

<div>

## <a name="to-disable-the-archiving-disclaimer"></a>停用封存放棄免責聲明

  - 若要停用封存免責聲明，請將**EnableArchivingDisclaimer**屬性的值設定為 False （$False）：
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

