---
title: 建立或修改用戶端版本配置設定的集合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a collection of client version configuration settings
ms:assetid: 4e6faffd-a36f-40f1-8734-78d84b7df921
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898477(v=OCS.15)
ms:contentKeyID: 50873757
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 84df13c7abbc98cbb90c5b59a6b0717deb855e28
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977810"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-client-version-configuration-settings-in-lync-server-2013"></a>在 Lync Server 2013 中建立或修改用戶端版本配置設定的集合

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

用戶端版本設定可用來開啟或關閉用戶端版本控制。 全域用戶端版本設定會安裝 Lync Server，並用於針對整個伺服器部署啟用或停用用戶端版本控制。 您也可以為個別網站設定用戶端版本配置設定。 您可以從 Lync Server 2013 [控制台] 或 [Lync Server 2013 管理命令介面] 建立或修改用戶端版本配置設定。

<div>


> [!NOTE]
> 由於匿名使用者不會與使用者、網站或服務產生關聯，因此匿名使用者只會受全域層級的原則影響。



</div>

<div>

## <a name="to-create-or-modify-client-version-configuration-settings-by-using-lync-server-control-panel"></a>使用 Lync Server [控制台] 建立或修改用戶端版本配置設定

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**用戶端**]，然後按一下 [**用戶端版本**設定] 瀏覽按鈕。

4.  在 [**用戶端版本**設定] 頁面上，執行下列動作：
    
      - 若要建立新的設定，請按一下 [**新增**]，選取網站，按一下 **[確定名稱]** ，然後更新設定。
    
      - 若要修改配置，請選取設定，按一下 [**編輯**]，按一下 [**顯示詳細資料**]，然後變更設定。

</div>

<div>

## <a name="creating-or-modifying-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 建立或修改用戶端版本配置設定

您可以使用**新的 CsClientVersionConfiguration** Cmdlet 來建立用戶端版本配置設定，並使用**CsClientVersionConfiguration** Cmdlet 加以修改。 這些 Cmdlet 都可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-create-a-new-collection-of-client-version-configuration-settings"></a>建立新的用戶端版本配置設定集合

  - 下列命令會建立套用至雷德蒙網站之用戶端版本配置設定的新集合。 在此範例中，雷德蒙網站的用戶端版本設定已停用。
    
        New-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $False

</div>

<div>

## <a name="to-enable-client-versioning-for-a-site"></a>啟用網站的用戶端版本設定

  - 這個命令可為雷蒙德網站啟用用戶端版本設定。
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<div>

## <a name="to-disable-client-versioning-throughout-the-organization"></a>在整個組織中停用用戶端版本設定

  - 在這個範例中，組織中使用的所有用戶端版本設定都停用用戶端版本設定。
    
        Get-CsClientVersionConfiguration | Set-CsClientVersionConfiguration  -Enabled $False

</div>

如需詳細資訊，請參閱適用于[新 CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg399029(v=OCS.15))和[CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg398623(v=OCS.15)) Cmdlet 的說明主題。

</div>

</div>

<span> </span>

</div>

</div>

</div>

