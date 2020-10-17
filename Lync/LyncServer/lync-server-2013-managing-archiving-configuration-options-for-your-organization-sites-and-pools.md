---
title: Lync Server 2013：管理組織、網站及集區的封存配置選項
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Archiving configuration options for your organization, sites, and pools
ms:assetid: 377a6f80-5f2b-4bc1-b507-e930a461fb1d
ms:mtpsurl: https://technet.microsoft.com/library/JJ204802(v=OCS.15)
ms:contentKeyID: 48183830
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0fd9b777f3c7dbfc008f0b985a9c1512aaeb52d2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498360"
---
# <a name="managing-archiving-configuration-options-in-lync-server-2013-for-your-organization-sites-and-pools"></a>為您的組織、網站及集區管理 Lync Server 2013 中的封存設定選項

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

在 [Lync Server 2013 控制台] 中，您可以使用封存設定來指定封存的實施方式。 這包含下列封存組態：

  - 當您部署 Lync Server 2013 時，預設會建立全域設定。

  - 選用的網站層級和集區層級組態，可建立及用於指定針對特定網站或集區如何實作封存。

您一開始部署封存時會設定封存組態，但是在部署後可以變更、新增及刪除組態。 在 [Lync Server 2013 控制台] 中，您可以**使用 [封存****與監控**] 群組的 [封存設定] 頁面，以管理全域層級、網站層級及集區層級的設定。 如需如何執行封存設定的詳細資訊（包括您可以指定哪些選項），以及封存設定的階層，請參閱規劃檔、部署檔或作業檔中的封存 [如何在 Lync Server 2013 中運作](lync-server-2013-how-archiving-works.md) 。

<div>


> [!NOTE]  
> 若要使用封存，您必須設定封存原則，以指定是否啟用內部通訊的封存、外部通訊的封存，或同時針對駐留在 Lync Server 2013 的所有使用者啟用封存。 依據預設，都不會啟用內部或外部通訊的封存。 如果您使用 Microsoft Exchange 整合，您必須啟用和設定 Exchange 2013，以支援所有駐留在 Exchange 2013 上的使用者，且其信箱已 In-Place 保留中的使用者。<BR>在啟用封存之前，應針對部署 (及選擇性針對特定網站和集區) 指定適當的封存組態，如本區段所述。 如需啟用封存的詳細資訊，請參閱部署檔中的設定 <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">和指派 Lync Server 2013</A> 中的封存原則。



</div>

**使用 Windows PowerShell Cmdlet 來查看封存設定資訊**

  - 您可以使用 Windows PowerShell 和 **Get-CsArchivingConfiguration** Cmdlet 來查看封存設定資訊。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。
    
    在 Lync Server 管理命令介面中，使用下列命令來查看所有封存設定設定的相關資訊：
    
        Get-CsArchivingConfiguration

<div>

## <a name="in-this-section"></a>本章節內容

  - [在 Lync Server 2013 中建立封存設定，以管理特定網站或集區的封存](lync-server-2013-creating-an-archiving-configuration-to-manage-archiving-for-specific-sites-or-pools.md)

  - [啟用或停用 Lync Server 2013 中的 IM 或會議會話的封存](lync-server-2013-enabling-or-disabling-archiving-of-im-or-conferencing-sessions.md)

  - [啟用或停用 Lync Server 2013 中的封存資料清除功能](lync-server-2013-enabling-or-disabling-the-purging-of-archived-data.md)

  - [啟用或停用 Lync Server 2013 中的重要模式，以在封存失敗時封鎖或允許 IM 和 web 會議會話](lync-server-2013-enable-disable-critical-mode.md)

  - [在 Lync Server 2013 中啟用或停用傳送封存免責聲明至同盟合作夥伴的功能](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [啟用或停用與 Exchange storage 的 Lync Server 2013 整合](lync-server-2013-enabling-or-disabling-integration-with-exchange-storage.md)

  - [在 Lync Server 2013 中刪除封存設定](lync-server-2013-deleting-an-archiving-configuration.md)

</div>

<div>

## <a name="see-also"></a>另請參閱


[管理 Lync Server 2013 封存](lync-server-2013-managing-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

