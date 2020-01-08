---
title: Lync Server 2013：準備 Active Directory 網域服務
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing Active Directory Domain Services
ms:assetid: 7b0d9aa4-f1ab-4578-b22f-b802b6ed1530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398607(v=OCS.15)
ms:contentKeyID: 48184583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7deb5594c0d3c009ee4b10565bc4dbe12f56d2c4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974485"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-active-directory-domain-services-in-lync-server-2013"></a>在 Lync Server 2013 中準備 Active Directory 網域服務

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-02-19_

在 Lync Server 2013 中，您可以使用 Lync Server 部署嚮導來準備 Active Directory 網域服務，或者您可以直接使用 Lync Server 管理命令介面 Cmdlet。 您也可以直接在網網域控制站上使用 ldifde 命令列工具，如本主題稍後所述。

Lync Server 部署嚮導會引導您完成每個 Active Directory 準備工作。 [部署嚮導] 會執行 Lync Server 管理命令介面 Cmdlet。 此工具適用于只有單一網域和單一林拓撲或其他類似拓撲的環境。

<div>


> [!IMPORTANT]  
> 您可以在網域或網域中部署 Lync Server，該網域控制站會執行32位版本的作業系統（如需詳細資訊，請參閱<A href="lync-server-2013-active-directory-infrastructure-requirements.md">Lync Server 2013 的 Active Directory 基礎結構需求</A>）。 不過，您無法使用 Lync Server 部署嚮導在這些環境中執行架構、林及網域準備，因為部署嚮導和支援檔案只有64位。 相反地，您可以在32位網網域控制站上使用 ldifde 和相關聯的 .ldf 檔案，以準備架構、林及網域。 請參閱本主題稍後的「使用 Cmdlet 與 cscript.exe」一節。



</div>

您可以使用 Lync Server 管理命令介面 Cmdlet 來遠端或更複雜的環境執行工作。

<div>

## <a name="active-directory-preparation-prerequisites"></a>Active Directory 準備先決條件

您必須在執行 Windows Server 2012、Windows Server 2012 R2 或 Windows Server 2008 R2 （含 SP1 （64））的電腦上執行 Active Directory 準備步驟。 Active Directory 準備需要 Lync Server Management 命令介面和 OCSCore。

必須具備下列元件，才能執行 Active Directory 準備工作：

  - Lync Server 核心元件（OCScore）
    
    <div>
    

    > [!NOTE]  
    > 如果您打算使用 Lync Server 管理命令介面進行 Active Directory 準備，您必須先執行 Lync Server 部署嚮導，才能安裝核心元件。

    
    </div>

  - Microsoft .NET Framework 4。5
    
    <div>
    

    > [!NOTE]  
    > 針對 Windows Server 2012 和 Windows Server 2012 R2，您可以使用 Server Manager 來安裝並啟動 .NET Framework 4.5。 如需詳細資訊，請參閱<A href="lync-server-2013-additional-software-requirements.md">Lync Server 2013 的其他軟體需求</A>中的 "Microsoft .net Framework 4.5"。 若是 Windows Server&nbsp;2008&nbsp;R2，請從 Microsoft 網站下載並安裝<A href="http://www.microsoft.com/en-us/download/details.aspx?id=30653">.net Framework 4.5</A> 。

    
    </div>

  - 遠端伺服器管理工具（RSAT）
    
    <div>
    

    > [!NOTE]  
    > 如果您在成員伺服器而不是在網網域控制站上執行 Active Directory 準備步驟，則需要使用一些 RSAT 工具。 從 [伺服器管理員] 中的 [AD DS] 和 [AD LDS 工具] 節點，安裝 AD DS 的管理單元和命令列工具，以及適用于 Windows PowerShell 的 Active Directory 模組。

    
    </div>

  - Microsoft Visual c + + 11 可轉散發元件
    
    <div>
    

    > [!NOTE]  
    > 如果電腦上尚未安裝此必備元件，安裝程式會提示您安裝。 套件是為您提供的，您不需要單獨取得套件。

    
    </div>

  - Windows PowerShell 3.0 （64位）
    
    針對 Windows Server 2012 和 Windows Server 2012 R2，Windows PowerShell 3.0 應該包含在您的 Lync Server 2013 安裝中。 若是 Windows Server 2008 R2，您需要安裝或升級至 Windows PowerShell 3.0。 如需詳細資訊，請參閱[安裝 Lync Server 2013 的 Windows PowerShell 3.0](lync-server-2013-installing-windows-powershell-3-0.md)

</div>

<div>

## <a name="administrator-rights-and-roles"></a>系統管理員權力與角色

下表顯示每個 Active Directory 準備工作所需的管理許可權和角色。

### <a name="user-rights-required-for-active-directory-preparation"></a>Active Directory 準備所需的使用者權利

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>過程</th>
<th>權力或角色</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>架構準備</p></td>
<td><p>目錄林根網域的架構管理員群組的成員，以及架構主機上的系統管理員許可權</p></td>
</tr>
<tr class="even">
<td><p>林準備</p></td>
<td><p>林的 [企業管理員] 群組成員</p></td>
</tr>
<tr class="odd">
<td><p>網域準備</p></td>
<td><p>指定網域的 [企業管理員] 或 [網域管理員] 群組成員</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="active-directory-preparation-cmdlets"></a>Active Directory 準備 Cmdlet

下表將用來準備 AD DS 的 Lync Server 管理命令介面 Cmdlet 與用來在 Microsoft Office 通訊伺服器 2007 R2 中用來準備 AD DS 的 LcsCmd 命令進行比較。

### <a name="cmdlets-compared-to-lcscmd"></a>與 LcsCmd 比較的 Cmdlet

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Cmdlet</th>
<th>LcsCmd</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Install-CsAdServerSchema</p></td>
<td><p>Lcscmd/forest/action： SchemaPrep/SchemaType： Server</p></td>
</tr>
<tr class="even">
<td><p>CsAdServerSchema</p></td>
<td><p>Lcscmd/forest/action： CheckSchemaPrepState</p></td>
</tr>
<tr class="odd">
<td><p>Enable-CsAdForest</p></td>
<td><p>Lcscmd/forest/action： ForestPrep</p></td>
</tr>
<tr class="even">
<td><p>Disable-CsAdForest</p></td>
<td><p>Lcscmd/forest/action： ForestUnprep</p></td>
</tr>
<tr class="odd">
<td><p>CsAdForest</p></td>
<td><p>Lcscmd/forest/action： CheckForestPrepState</p></td>
</tr>
<tr class="even">
<td><p>Enable-CsAdDomain</p></td>
<td><p>Lcscmd/domain/action： [已準備]</p></td>
</tr>
<tr class="odd">
<td><p>Disable-CsAdDomain</p></td>
<td><p>Lcscmd/domain/action： DomainUnprep</p></td>
</tr>
<tr class="even">
<td><p>CsAdDomain</p></td>
<td><p>Lcscmd/domain/action： CheckDomainPrepState</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="locked-down-active-directory-requirements"></a>已鎖定 Active Directory 需求

如果您的組織中必須停用 [許可權繼承] 或 [驗證的使用者] 許可權，您必須在網域準備期間執行其他步驟。 如需詳細資訊，請參閱[在 Lync Server 2013 中準備鎖定的 Active Directory 網域服務](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md)。

</div>

<div>

## <a name="custom-container-permissions"></a>自訂容器許可權

如果您的組織使用的是自訂容器，而不是三個內建的容器（也就是使用者、電腦及網網域控制站），您必須為 [已驗證使用者] 群組的自訂容器授與讀取權限。 網域準備必須具備容器的讀取權。 如需詳細資訊，請參閱[準備 Lync Server 2013 的網域](lync-server-2013-preparing-domains.md)。

</div>

<div>

## <a name="using-cmdlets-and-ldifdeexe"></a>使用 Cmdlet 和 Ldifde

Lync Server 部署嚮導中的 [**準備架構**] 步驟，且**安裝 CsAdServerSchema** Cmdlet 會在執行64位作業系統的網網域控制站上延伸 Active Directory 架構。 如果您需要在執行32位作業系統的網網域控制站上延伸 Active Directory 架構，您可以從成員伺服器遠端執行**安裝 CsAdServerSchema** Cmdlet （建議的方法）。 不過，如果您需要直接在網網域控制站上執行架構準備，您可以使用 Ldifde 工具匯入架構檔案。 Ldifde 工具隨附于大多數版本的 Windows 作業系統。

如果您使用 Ldifde 匯入架構檔案，無論您是從舊版本進行遷移或執行全新安裝，都必須匯入所有四個檔案。 您必須以下列順序匯入它們：

1.  ExternalSchema

2.  ServerSchema

3.  BackCompatSchema

4.  VersionSchema

<div>


> [!NOTE]  
> 四個 .ldf 檔案位於您的安裝媒體或下載的 \Support\Schema 目錄中。



</div>

若要使用 Ldifde 匯入架構主機所在的網網域控制站上的四個架構檔案，請使用下列格式：

    ldifde -i -v -k -s <DCName> -f <Schema filename> -c DC=X <defaultNamingContext> -j logFilePath -b <administrator account> <logon domain> <password>

例如：

    ldifde -i -v -k -s DC1 -f ServerSchema.ldf -c DC=X "DC=contoso,DC=com" -j C:\BatchImportLogFile -b Administrator contoso password

<div>


> [!NOTE]  
> 如果您是以不同的使用者身分登入，請使用 b 參數。 如需有關所需使用者許可權的詳細資訊，請參閱本主題先前的「管理員權力與角色」一節。



</div>

若要使用 Ldifde 匯入非架構主機的網網域控制站上的四個架構檔案，請使用下列格式：

    ldifde -i -v -k -s <SchemaMasterFQDN> -f <Schema filename> -c DC=X <rootDomainNamingContext> -j logFilePath -b <administrator account> <domain> <password>

如需使用 Ldifde 的詳細資訊，請參閱 Microsoft 知識庫文章237677：「使用 LDIFDE 將目錄物件匯入及匯出到 Active Directory [http://go.microsoft.com/fwlink/p/?linkId=132204](http://go.microsoft.com/fwlink/p/?linkid=132204)」。

</div>

<div>

## <a name="in-this-section"></a>本節內容

  - [在 Lync Server 2013 中準備 Active Directory 結構描述](lync-server-2013-preparing-the-active-directory-schema.md)

  - [為 Lync Server 2013 準備樹系](lync-server-2013-preparing-the-forest.md)

  - [針對 Lync Server 2013 準備網域](lync-server-2013-preparing-domains.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

