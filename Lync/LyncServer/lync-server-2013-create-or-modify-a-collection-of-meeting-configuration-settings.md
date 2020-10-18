---
title: 建立或修改會議配置設定的集合
description: 建立或修改會議配置設定的集合。
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
ms.openlocfilehash: 51dd68b3d149e5a96628fc3343d0d7eb3ae8020d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578239"
---
# <a name="create-or-modify-a-collection-of-meeting-configuration-settings-in-lync-server-2013"></a>在 Lync Server 2013 中建立或修改會議配置設定的集合

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

您可以使用 [會議設定] 頁面上的設定來定義會議加入體驗的各種特性。 根據預設，全域設定會定義加入體驗。 您也可以建立網站層級與集區層級會議加入設定。 如果您建立集區層級設定，這些設定會套用至該集區所主控的所有會議。 如果您未建立集區層級設定，則會套用網站層級設定（如果有的話）。 如果您未定義網站層級設定，全域設定會套用至所有會議。

<div>

## <a name="to-create-new-meeting-join-settings"></a>若要建立新的會議加入設定

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 [ **會議** ]，然後按一下 [ **會議**設定]。

4.  在 [ **會議** 設定] 頁面上，按一下 [ **新增**]，然後執行下列其中一項動作：
    
      - 若要建立網站層級原則，請按一下 [ **網站**設定]。 在 [ **選取網站** ] 搜尋欄位中，輸入您要定義會議加入設定之網站的全部或部分名稱。 在產生的網站清單中，按一下您想要的網站，然後按一下 **[確定]**。
    
      - 若要建立集區層級原則，請按一下 [ **集**區設定]。 在 [ **選取服務** ] 搜尋欄位中，輸入您要定義會議加入設定之集區服務的全部或部分名稱。 在產生的服務清單中，按一下您想要的集區，然後按一下 **[確定]**。

5.  若要透過會議廳從公用交換電話網路 (PSTN) 傳送從公用交換電話網路撥號的參與者，請清除 [ **PSTN 來電者旁路會議廳** ] 核取方塊。 根據預設，從 PSTN 撥入的參與者會直接進入會議。

6.  若要設定在會議中誰可以是簡報者，請在 [ **指定為簡報者**] 中，執行下列其中一項動作：
    
      - 若不允許召集人以外的任何人員成為簡報者，請按一下 [ **無**]。
    
      - 若只要允許屬於組織成員的參與者成為簡報者，請按一下 [ **公司**]。 這是預設設定。
    
      - 若要允許任何參與者成為簡報者，請按一下 [ **所有人**]。

7.  若要讓召集人在排程會議時選取會議類型，請清除 [ **依預設指派會議類型** ] 核取方塊。 依預設，會自動指派會議類型。

8.  若要防止匿名 (未驗證的使用者自動獲准) 使用者，請清除 [ **預設會承認匿名使用者** ] 核取方塊。 根據預設，匿名使用者會自動獲准參加會議。

9.  若要自訂傳送給參與者的會議邀請，請執行下列動作。 請注意，URLs 和自訂頁腳文字的最大長度為1KB。 除了 [說明 **URL**] 之外，如果您沒有指定自訂專案的值，這些自訂專案不會包含在會議中。 如果不包含自訂的 help URL，則會在邀請中顯示 Lync 的預設說明 URL。
    
      - 若要自訂出現在會議邀請中的標誌，請在 [ **標誌 URL**] 中輸入標誌的位置。
        
        <div>
        

        > [!NOTE]
        > 此徽標必須是大小為 188 x 30 圖元的 GIF 或 JPG 影像。

        
        </div>
    
      - 若要自訂出現在會議邀請中的解說文字，請在 [說明 **URL**] 中輸入説明文字的位置。
    
      - 若要自訂出現在會議邀請中的法律文字，請在 [ **合法文字 URL**] 中輸入法律文字的位置。
    
      - 若要自訂出現在會議邀請中的頁腳文字，請在 [ **自訂頁腳文字**] 中輸入文字。

10. 按一下 **[認可]**。

</div>

<div>

## <a name="to-modify-an-existing-collection-of-meeting-configurations"></a>修改現有會議組態集合

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 [ **會議** ]，然後按一下 [ **會議**設定]。

4.  在會議設定清單中，按一下您要變更的設定，然後按一下 [ **編輯**]，再按一下 [ **顯示詳細資料**]。

5.  在 [ **編輯會議**設定] 中，修改設定名稱以外的任何設定，但無法修改。

6.  按一下 **[認可]**。

</div>

<div>

## <a name="creating-new-meeting-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 建立新的會議配置設定

您只能使用 Windows PowerShell 和 New-CsMeetingConfiguration 指令程式) ，在網站範圍上建立會議設定設定 (。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。

<div>

## <a name="to-create-meeting-configuration-settings-that-use-the-default-values"></a>若要建立使用預設值的會議設定

  - 這個命令會為 Redmond 網站建立一組新的會議配置設定：
    
        New-CsMeetingConfiguration -Identity "site:Redmond"
    
    由於上述命令中未指定任何 (必要 Identity 參數) 以外的參數，因此新的會議設定會使用其所有屬性的預設值。

</div>

<div>

## <a name="to-change-a-property-value-when-creating-meeting-configuration-settings"></a>在建立會議設定設定時變更屬性值

  - 若要建立使用不同屬性質的設定，只需要加入適當的參數和參數值即可。 例如，若要建立會議設定的集合，根據預設，承認所有人都可以加入會議，以供簡報者使用類似如下的命令：
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-meeting-configuration-settings"></a>在建立會議設定設定時變更多個屬性值

  - 多項屬性值可透過加入多個參數加以修改。 例如，此命令會 admits 所有人做為簡報者會議，也會強制 PSTN 使用者在大廳等候後，直到他們正式獲准參加會議為止：
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True

</div>

如需詳細資訊，請參閱 [New-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg398065(v=OCS.15)) Cmdlet 的 [說明] 主題。

</div>

</div>

<span> </span>

</div>

</div>

</div>

