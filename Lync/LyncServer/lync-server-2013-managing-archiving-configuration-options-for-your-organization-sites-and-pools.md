---
title: Lync Server 2013：管理組織、網站和池的封存配置選項
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing Archiving configuration options for your organization, sites, and pools
ms:assetid: 377a6f80-5f2b-4bc1-b507-e930a461fb1d
ms:mtpsurl: https://technet.microsoft.com/library/JJ204802(v=OCS.15)
ms:contentKeyID: 48183830
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d27ea110c345be8963c5b3be3fa8b761e1b3727
ms.sourcegitcommit: 0119af282f53f49c4ab6e01c3319d01bc6fdad2c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/14/2020
ms.locfileid: "41111717"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-archiving-configuration-options-in-lync-server-2013-for-your-organization-sites-and-pools"></a>管理您組織、網站和池的 Lync Server 2013 中的封存配置選項

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

在 Lync Server 2013 的 [控制台] 中，您可以使用 [封存設定] 來指定歸檔的實施方式。 這包括下列歸檔設定：

  - 當您部署 Lync Server 2013 時預設會建立的全域配置。

  - 您可以建立及用來指定如何針對特定網站或池實施封存的選擇性網站層級和池層級設定。

您最初是在部署封存時設定封存配置，但您可以在部署之後變更、新增及刪除配置。 在 Lync Server 2013**的 [控制台**] 中，您可以使用 [封存**與監控**] 群組的 [封存設定] 頁面，來管理全域層級、網站層級和池層級的設定。 如需有關如何實施封存配置的詳細資料，包括您可以指定哪些選項，以及歸檔設定的階層，請參閱規劃檔、部署檔或作業檔中的[存檔在 Lync Server 2013 中的運作方式](lync-server-2013-how-archiving-works.md)。

<div>


> [!NOTE]  
> 若要使用封存，您必須設定存檔原則，以指定是否要針對內部通訊啟用封存，或針對所有駐留在 Lync Server 2013 的使用者，進行這兩者。 根據預設，不會針對內部或外部通訊啟用封存。 如果您使用的是 Microsoft Exchange 整合，您必須啟用並設定 Exchange 2013，以支援所有駐留在已將其信箱放在就地保留中之 Exchange 2013 的使用者的存檔。<BR>在啟用封存之前，您應該為您的部署指定適當的歸檔設定，也可以針對特定的網站和池指定適當的存檔設定，如本節所述。 如需啟用封存的詳細資料，請參閱在部署檔中設定<A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">和指派 Lync Server 2013 中的存檔原則</A>。



</div>

**若要使用 Windows PowerShell Cmdlet 來查看封存配置資訊**

  - 您可以使用 Windows PowerShell 和**CsArchivingConfiguration** Cmdlet 來查看封存配置資訊。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)。
    
    在 Lync Server 管理命令介面中，請使用下列命令來查看所有存檔設定設定的相關資訊：
    
        Get-CsArchivingConfiguration

<div>

## <a name="in-this-section"></a>本節內容

  - [在 Lync Server 2013 中建立存檔設定，以管理特定網站或池中的存檔](lync-server-2013-creating-an-archiving-configuration-to-manage-archiving-for-specific-sites-or-pools.md)

  - [在 Lync Server 2013 中啟用或停用 IM 或會議會話的封存](lync-server-2013-enabling-or-disabling-archiving-of-im-or-conferencing-sessions.md)

  - [啟用或停用 Lync Server 2013 中已歸檔的資料清除](lync-server-2013-enabling-or-disabling-the-purging-of-archived-data.md)

  - [啟用或停用 Lync Server 2013 中的 [重要模式]，以封鎖或允許 IM 和網路會議會話（如果歸檔失敗）](lync-server-2013-enable-disable-critical-mode.md)

  - [在 Lync Server 2013 中啟用或停用傳送封存免責聲明至同盟合作夥伴的功能](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [啟用或停用 Lync Server 2013 與 Exchange 儲存空間的整合](lync-server-2013-enabling-or-disabling-integration-with-exchange-storage.md)

  - [在 Lync Server 2013 中刪除封存配置](lync-server-2013-deleting-an-archiving-configuration.md)

</div>

<div>

## <a name="see-also"></a>請參閱


[管理 Lync Server 2013 封存](lync-server-2013-managing-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

