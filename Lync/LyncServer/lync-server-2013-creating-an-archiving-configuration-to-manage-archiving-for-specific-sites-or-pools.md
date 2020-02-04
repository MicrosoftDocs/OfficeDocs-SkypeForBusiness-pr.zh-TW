---
title: Lync Server 2013：建立存檔設定以管理特定網站或池中的存檔
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
ms.openlocfilehash: 3b0495a15d19adba9ac21fb7817347a16b78bc13
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762741"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-an-archiving-configuration-in-lync-server-2013-to-manage-archiving-for-specific-sites-or-pools"></a>在 Lync Server 2013 中建立存檔設定，以管理特定網站或池中的存檔

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

在 Lync Server 2013 的 [控制台] 中，您可以使用封存配置來控制在您的部署中實現封存的方式。 這包括下列歸檔設定：

  - 當您部署 Lync Server 2013 時預設會建立的全域配置。

  - 您可以建立及用來指定如何針對特定網站或池實施封存的選擇性網站層級和池層級設定。

您最初是在部署封存時設定封存配置，但您可以在部署之後變更、新增及刪除配置。 如需有關如何實施封存配置的詳細資料，包括您可以指定哪些選項，以及歸檔設定的階層，請參閱規劃檔、部署檔或作業檔中的 [[在 Lync Server 2013 中的存檔運作方式](lync-server-2013-how-archiving-works.md)]。

<div>


> [!NOTE]  
> 若要使用封存，您必須設定封存原則，以指定是否要針對內部通訊啟用封存，或針對駐留在 Lync Server 2013 的使用者。 根據預設，不會針對內部或外部通訊啟用封存。 在任何原則中啟用封存前，您應該為您的部署指定適當的歸檔設定，也可以針對特定的網站和池指定適當的存檔配置，如本節所述。 如需啟用封存的詳細資料，請參閱在部署檔中設定<A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">和指派 Lync Server 2013 中的存檔原則</A>。<BR>如果您在部署存檔後決定要使用 Microsoft Exchange 整合來儲存 Exchange 2013 伺服器上的封存資料和檔案，且您的所有使用者都是位於 Exchange 2013 伺服器上，那麼您應該移除 SQL Server 資料庫配置從您的拓撲。 您必須使用拓撲 Builder 建立器。 如需詳細資訊，請參閱在作業檔中<A href="lync-server-2013-changing-archiving-database-options.md">變更 Lync Server 2013</A>中的封存資料庫選項。



</div>

<div>

## <a name="to-create-an-archiving-configuration-for-a-site-or-pool"></a>為網站或文件庫建立封存配置

1.  從指派給 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**監視及**封存]，然後按一下 [封存**配置**]。

4.  在 [**存檔**設定] 頁面上，按一下 [**新增**]，然後執行下列其中一項操作：
    
      - 若要建立網站封存設定，請按一下 [**網站**設定]，然後在 [**選取網站**] 中，選取要設定為要存檔的網站。
    
      - 若要建立池存檔設定，請按一下 [**池**設定]，然後在 [**選取池**] 中，選取要設定為要存檔的池。

5.  在 [**新增封存設定**] 的 [**存檔設定**] 下拉式清單方塊中，執行下列其中一項操作：
    
      - 若要只針對立即訊息（IM）會話啟用封存，請按一下 [封存**IM 會話**]。
    
      - 若要在 IM 會話和網路會議中同時啟用封存功能，請按一下 [封存**im 和網路會議會話**]。
    
      - 若要停用原則封存，請按一下 [**停**用封存]。

6.  此外，在 [新增封存]**設定**中，請執行下列動作：
    
      - 若要在封存無法使用時封鎖活動，請選取 [**如果封存失敗，封鎖立即訊息（IM）或 web 會議會話**] 核取方塊。
    
      - 若要使用 Microsoft Exchange Server 儲存存檔資料，請按一下 [ **Microsoft exchange 整合**] 核取方塊。
    
      - 若要啟用資料清除，請選取 [**啟用 [清除封存資料**] 核取方塊，然後執行下列其中一項操作：
        
          - 若要指定在特定天數後進行清除，請按一下 **[清除匯出的存檔資料]，並儲存在最長持續時間（天數）之後的儲存封存資料**，然後指定天數。
        
          - 若要限制清除以封存已匯出的資料，請按一下 [**僅清除匯出的存檔資料**]。

7.  按一下 [認可]****。

</div>

<div>

## <a name="creating-archiving-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 建立封存配置設定

您可以使用 Windows PowerShell 和 CsArchivingConfiguration Cmdlet 來建立封存配置設定。 這個 Cmdlet 可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-create-a-new-collection-of-archiving-configuration-settings-for-a-site"></a>若要建立新的網站封存配置設定集合

  - 下列命令會建立新的 [雷德蒙] 網站存檔設定的集合：
    
        New-CsArchivingConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-collection-of-archiving-configuration-settings-that-only-allow-im-archiving"></a>若要建立只允許 IM 存檔的新的封存設定設定集合

  - 因為在上述命令中沒有指定任何參數（強制身分識別參數以外），所以新的配置設定集合會將預設值用於其所有屬性。 若要建立使用不同屬性值的設定，只要包含適當的參數和參數值即可。 例如，若要建立一組封存設定，並根據預設，允許封存立即訊息會話，請只使用如下所示的命令：
    
        New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly"

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-archiving-configuration-settings"></a>若要在建立存檔設定時指定多個屬性值

  - 您可以透過包含多個參數來修改多個屬性值。 例如，這個命令會將新設定設為封存立即訊息會話，並封鎖封存服務的立即訊息無法使用：
    
        New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly" -BlockOnArchiveFailure $True

</div>

如需詳細資訊，請參閱[新版-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsArchivingConfiguration) Cmdlet 的說明主題。

</div>

<div>

## <a name="see-also"></a>請參閱


[存檔在 Lync Server 2013 中的運作方式](lync-server-2013-how-archiving-works.md)  


[管理您組織、網站和池的 Lync Server 2013 中的封存配置選項](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

