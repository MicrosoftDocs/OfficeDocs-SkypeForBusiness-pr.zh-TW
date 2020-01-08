---
title: Lync Server 2013：啟用或停用重要模式，以封鎖或允許 IM 和網路會議會話（如果歸檔失敗）
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling or disabling critical mode to block or allow IM and web conferencing sessions if Archiving fails
ms:assetid: fafdcd2e-b778-4ed5-a25f-09208aa3b699
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182609(v=OCS.15)
ms:contentKeyID: 48185927
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c690c235a3a753db8cc07cebbc8749a0d27c99f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975729"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-critical-mode-in-lync-server-2013-to-block-or-allow-im-and-web-conferencing-sessions-if-archiving-fails"></a>啟用或停用 Lync Server 2013 中的 [重要模式]，以封鎖或允許 IM 和網路會議會話（如果歸檔失敗）

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

在 Lync Server 2013 的 [控制台] 中，您可以使用 [封存設定] 來啟用和停用 [關鍵模式]。 這包括下列歸檔設定：

  - 當您部署 Lync Server 2013 時預設會建立的全域配置。

  - 您可以建立及用來指定如何針對特定網站或池實施封存的選擇性網站層級和池層級設定。

您最初是在部署封存時設定封存配置，但您可以在部署之後變更、新增及刪除配置。 如需有關如何實施封存配置的詳細資料，包括您可以指定哪些選項，以及歸檔設定的階層，請參閱規劃檔、部署檔或作業檔中的 [[在 Lync Server 2013 中的存檔運作方式](lync-server-2013-how-archiving-works.md)]。

<div>


> [!NOTE]  
> 若要使用封存，您必須設定封存原則，以指定是否要針對內部通訊啟用封存，或針對駐留在 Lync Server 2013 的使用者。 根據預設，不會針對內部或外部通訊啟用封存。 在任何原則中啟用封存前，您應該為您的部署指定適當的歸檔設定，也可以針對特定的網站和池指定適當的存檔配置，如本節所述。 如需啟用封存的詳細資料，請參閱在部署檔中設定<A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">和指派 Lync Server 2013 中的存檔原則</A>。<BR>如果您在部署存檔後決定要使用 Exchange Server 整合來儲存 Exchange 2013 伺服器上的封存資料和檔案，且您的所有使用者都是位於您的 Exchange 2013 伺服器上，那麼您應該移除 SQL Server 資料庫配置您的拓撲。 您必須使用拓撲 Builder 建立器。 如需詳細資訊，請參閱在作業檔中<A href="lync-server-2013-changing-archiving-database-options.md">變更 Lync Server 2013</A>中的封存資料庫選項。



</div>

<div>

## <a name="to-enable-or-disable-blocking-of-im-and-web-conferencing-sessions-if-archiving-fails"></a>若要啟用或停用封鎖 IM 和網路會議會話（如果封存失敗的話）

1.  從指派給 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**監視及**封存]，然後按一下 [封存**配置**]。

4.  在歸檔設定清單中，按一下適當的全域、網站或池設定的名稱，按一下 [**編輯**]，按一下 [**顯示詳細資料**]，然後執行下列動作：

5.  若要設定在發生失敗時封存的行為方式，請選取或清除 [**如果封存失敗，封鎖立即訊息（IM）或 web 會議會話**] 核取方塊。

6.  按一下 [認可]****。

</div>

<div>

## <a name="enabling-and-disabling-critical-mode-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 啟用和停用重要模式

您可以使用**CsArchivingConfiguration** Cmdlet 來啟用或停用重要模式。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-enable-critical-mode"></a>啟用 [關鍵] 模式

  - 若要啟用 [關鍵] 模式，請將 BlockOnArchiveFailure 屬性的值設定為 True （$True）。 例如：
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True

</div>

<div>

## <a name="to-disable-critical-mode"></a>停用關鍵模式

  - 若要停用 [關鍵模式]，請將 BlockOnArchiveFailure 屬性的值設定為 False （$False）。 例如：
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False

</div>

如需詳細資訊，請參閱[CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) Cmdlet 的說明主題。

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中變更封存資料庫選項](lync-server-2013-changing-archiving-database-options.md)  


[存檔在 Lync Server 2013 中的運作方式](lync-server-2013-how-archiving-works.md)  


[管理您組織、網站和池的 Lync Server 2013 中的封存配置選項](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

