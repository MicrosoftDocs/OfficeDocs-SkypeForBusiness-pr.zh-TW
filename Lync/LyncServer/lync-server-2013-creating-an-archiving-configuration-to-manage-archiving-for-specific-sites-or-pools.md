---
title: Lync Server 2013：建立封存設定以管理特定網站或集區的封存
description: Lync Server 2013：建立封存設定以管理特定網站或集區的封存。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating an Archiving configuration to manage Archiving for specific sites or pools
ms:assetid: c5c864a6-96c7-4bbb-ab7c-61eb1744246c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205251(v=OCS.15)
ms:contentKeyID: 48185361
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ab19f2d8900693ef0fcb14d8f6d862b22c355bd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563109"
---
# <a name="creating-an-archiving-configuration-in-lync-server-2013-to-manage-archiving-for-specific-sites-or-pools"></a>在 Lync Server 2013 中建立封存設定，以管理特定網站或集區的封存

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

在 [Lync Server 2013 控制台] 中，您可以使用封存設定來控制如何在部署中實施封存。 這包含下列封存組態：

  - 當您部署 Lync Server 2013 時，預設會建立全域設定。

  - 選用的網站層級和集區層級組態，可建立及用於指定針對特定網站或集區如何實作封存。

您一開始部署封存時會設定封存組態，但是在部署後可以變更、新增及刪除組態。 如需如何執行封存設定的詳細資訊，包括您可以指定哪些選項以及封存設定的階層，請參閱規劃檔、部署檔或作業檔中的封存 [如何在 Lync Server 2013 中運作](lync-server-2013-how-archiving-works.md) 。

<div>


> [!NOTE]  
> 若要使用封存，您必須設定封存原則，以指定是否啟用內部通訊、外部通訊或同時適用于 Lync Server 2013 的使用者的封存。 依據預設，都不會啟用內部或外部通訊的封存。 在任何原則中啟用封存之前，您應該為您的部署指定適當的封存設定，以及針對特定網站和集區（選用）指定適當的封存設定，如本節所述。 如需啟用封存的詳細資訊，請參閱部署檔中的設定 <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">和指派 Lync Server 2013</A> 中的封存原則。<BR>如果您在部署封存後決定要使用 Microsoft Exchange 整合將封存資料和檔案儲存在 Exchange 2013 伺服器上，而且所有使用者都位於 Exchange 2013 伺服器上，則應該從拓撲中移除 SQL Server 資料庫設定。 您必須使用拓撲產生器來執行這項作業。 如需詳細資訊，請參閱 Operations 檔中的 <A href="lync-server-2013-changing-archiving-database-options.md">變更 Lync Server 2013</A> 中的封存資料庫選項。



</div>

<div>

## <a name="to-create-an-archiving-configuration-for-a-site-or-pool"></a>為網站或集區建立封存設定

1.  使用指派到 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中 **，按一下 [****監視與**封存]，然後按一下 [封存設定]。

4.  在 [ **封存** 設定] 頁面上，按一下 [ **新增**]，然後執行下列其中一項操作：
    
      - 若要建立網站封存設定，請按一下 [ **網站** 設定]，然後在 [ **選取網站**] 中選取要設定封存的網站。
    
      - 若要建立集區封存設定，請按一下 [ **集** 區設定]，然後在 [ **選取集**區] 中選取要設定封存的集區。

5.  在 **[建立新的封存設定]** 的 **[封存設定]** 下拉式清單方塊中，執行下列其中一項作業：
    
      - 若只要啟用立即訊息 (IM) 工作階段的封存，請按一下 **[封存 IM 工作階段]**。
    
      - 若要同時啟用 IM 會話和 web 會議的封存，請按一下 [封存 **im 和 web 會議會話**]。
    
      - 若要停用原則的封存，請按一下 **[停用封存]**。

6.  此外，在 **[建立新的封存設定]** 中，執行下列動作：
    
      - 若要在封存無法使用時封鎖活動，請選取 **[封存失敗時封鎖立即訊息 (IM) 和 Web 會議工作階段]** 核取方塊。
    
      - 若要使用 Microsoft Exchange Server 儲存封存資料，請按一下 [ **Microsoft exchange 整合** ] 核取方塊。
    
      - 若要啟用資料清除，請選取 **[啟用封存資料的清除]** 核取方塊，然後執行下列其中一項作業：
        
          - 若要指定在特定天數後進行清除，請按一下 **[在最大持續期限 (天) 後清除匯出的封存資料和儲存的封存資料]**，然後指定天數。
        
          - 若要限制只清除已匯出的封存資料，請按一下 **[只清除匯出的封存資料]**。

7.  按一下 **[認可]**。

</div>

<div>

## <a name="creating-archiving-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 建立封存配置設定

您可以使用 Windows PowerShell 和 New-CsArchivingConfiguration Cmdlet 來建立封存設定設定。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。

<div>

## <a name="to-create-a-new-collection-of-archiving-configuration-settings-for-a-site"></a>為網站建立新的封存配置設定集合

  - 下列命令會為 Redmond 網站建立新的封存配置設定集合：
    
        New-CsArchivingConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-collection-of-archiving-configuration-settings-that-only-allow-im-archiving"></a>若要建立只允許 IM 封存的新封存配置設定集合

  - 因為上述命令未指定參數 (除了必要的 Identity 參數)，新的組態設定集合會將預設值用於其所有屬性。 若要使用不同的屬性值來建立設定，只要包含適當的參數及參數值即可。 例如，若要建立封存設定的集合，根據預設，允許封存立即訊息會話，只會使用類似下列的命令：
    
        New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly"

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-archiving-configuration-settings"></a>在建立封存配置設定時指定多個屬性值

  - 多項屬性值可透過加入多個參數加以修改。 例如，此命令會將新設定設定為封存立即訊息會話，並封鎖封存服務的立即訊息無法使用：
    
        New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly" -BlockOnArchiveFailure $True

</div>

如需詳細資訊，請參閱 [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsArchivingConfiguration) Cmdlet 的 [說明] 主題。

</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 中的封存運作方式](lync-server-2013-how-archiving-works.md)  


[為您的組織、網站及集區管理 Lync Server 2013 中的封存設定選項](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

