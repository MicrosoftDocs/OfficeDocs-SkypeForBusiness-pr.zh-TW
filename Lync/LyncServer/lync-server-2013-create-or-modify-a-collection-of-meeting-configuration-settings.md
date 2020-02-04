---
title: 建立或修改會議配置設定的集合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of meeting configuration settings
ms:assetid: ce6773c1-a0d5-4405-8e32-33a6f3a46a1a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721889(v=OCS.15)
ms:contentKeyID: 49733822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a5f80066a68b45e062a351478bea93a5c2e8fd0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763335"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-meeting-configuration-settings-in-lync-server-2013"></a>在 Lync Server 2013 中建立或修改會議配置設定的集合

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

您可以使用 [會議設定] 頁面上的設定來定義會議加入體驗的各種特性。 根據預設，全域設定會定義連接體驗。 您也可以建立網站層級和池層次會議加入設定。 如果您建立了 [pool] 層級設定，這些設定就會套用至該池子主持的所有會議。 如果您沒有建立池層級設定，就會套用網站層級設定（如果存在的話）。 如果您沒有定義網站層級設定，全域設定就會套用至所有會議。

<div>

## <a name="to-create-new-meeting-join-settings"></a>建立新的會議加入設定

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**會議**]，然後按一下 [**會議配置**]。

4.  在 [**會議**設定] 頁面上，按一下 [**新增**]，然後執行下列其中一項操作：
    
      - 若要建立網站層級原則，按一下 [**網站**設定]。 在 [**選取網站**搜尋] 欄位中，輸入您要定義會議加入設定的網站名稱全部或部分名稱。 在產生的網站清單中，按一下您想要的網站，然後按一下 **[確定]**。
    
      - 若要建立池層級原則，請按一下 [**池**設定]。 在 [**選取服務**搜尋] 欄位中，輸入您要定義會議加入設定的全部或部分的 [池服務] 名稱。 在產生的服務清單中，按一下您想要的 [池]，然後按一下 **[確定]**。

5.  若要傳送透過大廳從公用交換電話網絡（PSTN）撥入的參與者，請清除**PSTN 呼叫者略過大廳**核取方塊。 根據預設，從 PSTN 撥入的參與者會直接進入會議。

6.  若要設定在會議中可成為簡報者的人員，請在 [**指定為簡報者**] 中，執行下列其中一項操作：
    
      - 若要不允許召集人以外的任何人成為簡報者，請按一下 [**無**]。
    
      - 若要只允許作為您組織成員的參與者成為簡報者，請按一下 [**公司**]。 這是預設設定。
    
      - 若要讓任何參與者成為簡報者，請按一下 [**所有人**]。

7.  若要讓召集人在排程會議時選取會議類型，請清除 [**預設為指派的會議類型**] 核取方塊。 根據預設，會自動指派會議類型。

8.  若要防止匿名（未經授權）使用者自動獲准，請清除 [**預設承認匿名使用者**] 核取方塊。 根據預設，匿名使用者會自動獲准參加會議。

9.  若要自訂傳送給參與者的會議邀請，請執行下列動作。 請注意，Url 和自訂頁尾文字的最大長度為1KB。 除了說明**URL**之外，如果您沒有指定自訂專案的值，就不會包含在會議中。 如果您不包含自訂的說明 URL，則 Lync 的預設說明 URL 將會顯示在邀請中。
    
      - 若要自訂會議邀請中出現的標誌，請在 [**標誌 URL**] 中輸入標誌的位置。
        
        <div>
        

        > [!NOTE]
        > 標誌必須是一個大小為 188 x 30 圖元的 GIF 或 JPG 影像。

        
        </div>
    
      - 若要自訂會議邀請中出現的解說文字，請在 [說明] **URL**中輸入解說文字的位置。
    
      - 若要自訂會議邀請中出現的法律文字，請在 [**合法文字 URL**] 中輸入法律文字的位置。
    
      - 若要自訂會議邀請中顯示的頁尾文字，請在 [**自訂頁尾文字**] 中輸入文字。

10. 按一下 [認可]****。

</div>

<div>

## <a name="to-modify-an-existing-collection-of-meeting-configurations"></a>修改現有的會議組態集合

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**會議**]，然後按一下 [**會議配置**]。

4.  在會議配置清單中，按一下您要變更的設定，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。

5.  在 [**編輯會議**設定] 中，修改任何設定的設定，除了不能修改的配置名稱。

6.  按一下 [認可]****。

</div>

<div>

## <a name="creating-new-meeting-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 建立新的會議配置設定

您可以使用 Windows PowerShell 和 CsMeetingConfiguration Cmdlet 來建立會議設定設定（僅限在網站範圍內）。 這個 Cmdlet 可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-create-meeting-configuration-settings-that-use-the-default-values"></a>若要建立使用預設值的會議設定設定

  - 這個命令會針對雷德蒙的網站建立一組新的會議配置設定：
    
        New-CsMeetingConfiguration -Identity "site:Redmond"
    
    因為在上述命令中沒有指定任何參數（除了是強制身分識別參數），所以新的會議設定會針對其所有屬性使用預設值。

</div>

<div>

## <a name="to-change-a-property-value-when-creating-meeting-configuration-settings"></a>若要在建立會議設定設定時變更屬性值

  - 若要建立使用不同屬性值的設定，只要包含適當的參數和參數值即可。 例如，若要建立會議設定的集合，根據預設，承認所有人都可以以演講者身分參與會議，請使用如下所示的命令：
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-meeting-configuration-settings"></a>若要在建立會議設定設定時變更多個屬性值

  - 您可以透過包含多個參數來修改多個屬性值。 例如，此命令會允許所有人加入會議，同時也會強制 PSTN 使用者在大廳等候，直到正式獲准參加會議：
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True

</div>

如需詳細資訊，請參閱[新版-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg398065(v=OCS.15)) Cmdlet 的說明主題。

</div>

</div>

<span> </span>

</div>

</div>

</div>

