---
title: 在 Lync Server 2013 中設定商務用 Skype 用戶端
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure the client experience
ms:assetid: 61e783f1-24f4-430b-ae52-c76a4d206dc7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn954919(v=OCS.15)
ms:contentKeyID: 65227958
ms.date: 09/18/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b89457c35bc9c9c0150b84ab34f4103776206ad
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180776"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-the-client-experience-with-skype-for-business"></a>使用商務用 Skype 設定用戶端經驗

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015-09-17_

**摘要：** 本主題說明如何在 Lync Server 2013 環境中為商務用 Skype 用戶端使用者設定用戶端經驗。 您可以設定用戶端體驗，只有在您執行 Lync Server 2013 時已安裝12月2014累積更新 (5.0.8308.857) 或更新版本。 如需更新 Lync Server 2013 的詳細資訊，請參閱[Lync server 2013 的更新](https://go.microsoft.com/fwlink/p/?linkid=532651)。

商務用 skype 提供以 Skype 消費者產品經驗為基礎的新使用者經驗。 除了 Lync 的所有功能之外，商務用 Skype 也會透過簡化的控制項及熟悉的圖示來提供新功能。 如需有關新用戶端體驗的詳細資訊，請參閱[Lync 現在是商務用 Skype--查看](https://go.microsoft.com/fwlink/?linkid=529022)最近更新。

Lync Server 2013 支援新的商務用 Skype 用戶端體驗和 Lync 用戶端經驗。 身為管理員，您可以為使用者選擇喜歡的用戶端體驗。 例如，您可能想要部署 Lync 用戶端體驗，直到貴組織中的使用者已完全訓練新的商務用 Skype 體驗。 或者，如果您尚未將所有使用者升級至商務用 Skype Server 2015，您可能想要在所有使用者都升級至新伺服器之前，都有相同的用戶端經驗。

<div>


> [!IMPORTANT]  
> 如果您的組織已部署商務用 Skype Server 2015 和 Lync Server 2013，則預設用戶端體驗會因伺服器版本和 UI 設定而異。 當使用者第一次啟動商務用 Skype 時，他們會永遠看到商務用 Skype 使用者介面--即使您已選取 Lync 使用者介面也是一樣。 幾分鐘後，系統會要求使用者切換至 Lync 模式。 如需詳細資訊，請參閱本主題稍後的<STRONG>第一次啟動用戶端行為</STRONG>。



</div>

<div>


> [!NOTE]  
> Lync 2013 用戶端體驗不是商務用 Skype 2016 用戶端版本的選項。 在您嘗試設定用戶端環境以使用 Lync 2013 用戶端之前，請檢查用戶端版本，以確保其不是以數位16開頭;例如： x.x.x。



</div>

<div>

## <a name="configure-the-client-experience"></a>設定用戶端體驗

您可以使用**Set-CSClientPolicy** Cmdlet 搭配 EnableSkypeUI 參數，指定組織中的使用者所看到的用戶端經驗。 下列命令會為組織中受全域原則影響的所有使用者選取商務用 Skype 用戶端體驗 (請記住，網站或使用者特定原則會覆寫全域原則) ：

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $true

下一個命令會為組織中的所有使用者選取受全域原則影響的 Lync 用戶端體驗：

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $false

下一個命令會為 Redmond 網站內的所有使用者選取商務用 Skype 用戶端體驗：

    Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true

如果您想要為組織內的特定使用者設定用戶端經驗，您可以使用**New-CsClientPolicy** Cmdlet 來建立新的使用者原則，然後使用**Grant-CsClientPolicy** Cmdlet 將原則指派給特定使用者。

例如，下列命令會建立新的用戶端原則 SalesClientUI，以選取商務用 Skype 用戶端體驗：

    New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true

下一個命令會將原則 SalesClientUI 指派給銷售部門的所有成員：

    Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI

</div>

<div>

## <a name="first-launch-client-behaviors"></a>第一次啟動用戶端行為

根據預設，當使用者第一次啟動商務用 Skype 時，他們會永遠看到商務用 Skype 使用者介面--即使您已透過將 EnableSkypeUI 參數的值設為 $False，如先前所述，您已選取 Lync 用戶端經驗。 幾分鐘後，系統會要求使用者切換至 Lync 模式。

當使用者第一次啟動商務用 Skype 用戶端時，如果您想要顯示 Lync 使用者介面，請在更新後第一次啟動用戶端之前，先執行下列步驟：

1.  確認的值 `EnableSkypeUI` 已設定為在您使用的原則中 $False，如先前所述。

2.  更新使用者電腦上的系統登錄。 您應該在使用者第一次啟動商務用 Skype 用戶端之前執行此作業，而且您應該只執行一次。 如需如何建立群組原則物件以更新加入網域之電腦上之登錄的詳細資訊，請參閱本主題稍後的章節。
    
    在 [ ** \[ HKEY \_ 目前的 \_ 使用者 \\ 軟體] \\ Microsoft \\ Office \\ \] Lync**金鑰中，建立新的**二進位**值。
    
    **值名稱**必須是**EnableSkypeUI**，且**數值資料**必須設定為**00 00 00 00**。
    
    索引鍵應該如下所示：
    
        [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
        "CanSharePptInCollab"=dword:00000001
        "CanShareOneNoteInCollab"=dword:00000001
        "CanAppShareInCollab"=dword:00000001
        "EnableSkypeUI"=hex:00,00,00,00

當使用者第一次啟動商務用 Skype 用戶端時，即會顯示 Lync 使用者介面。

<div>

## <a name="control-the-display-of-the-welcome-screen-tutorial"></a>控制歡迎使用畫面教學課程的顯示

當使用者開啟商務用 Skype 用戶端時，預設行為是顯示歡迎畫面，其中包含*大多數人員所要求的7個快速秘訣*。 您可以在用戶端電腦上新增下列登錄值，關閉 [歡迎] 畫面，但仍允許使用者存取教學課程：

在 [ ** \[ HKEY \_ 目前的 \_ 使用者 \\ 軟體] \\ Microsoft \\ Office \\ 15.0 \\ Lync \] **機碼中，建立新的**DWORD (32 位) 值**。 **值名稱**必須是**IsBasicTutorialSeenByUser**，且**數值資料**必須設定為**1**。

索引鍵應該如下所示：

    "IsBasicTutorialSeenByUser"=dword:00000001

</div>

<div>

## <a name="turn-off-the-client-tutorial"></a>關閉用戶端教學課程

如果您不想讓使用者能夠存取教學課程，您可以使用下列登錄值來關閉用戶端教學課程：

在 [ ** \[ HKEY \_ 目前的 \_ 使用者 \\ 軟體] \\ Microsoft \\ Office \\ 15.0 \\ Lync \] **機碼中，建立新的**DWORD (32 位) 值**。 **值名稱**必須是**TutorialFeatureEnabled**，且**數值資料**必須設定為**0**。

    "TutorialFeatureEnabled"=dword:00000000

您可以將**數值資料**設為**1**，以重新開啟教學課程。

</div>

</div>

<div>

## <a name="default-client-experiences"></a>預設用戶端體驗

如果您的組織同時已部署商務用 Skype Server 2015 和 Lync Server，用戶端經驗會因伺服器版本和 Skype UI 設定而有所不同。 下表顯示以伺服器版本及 UI 設定為基礎的初始用戶端體驗：


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>伺服器版本</p></th>
<th><p>EnableSkypeUI 設定</p></th>
<th><p>用戶端經驗</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>商務用 Skype Server 2015</p></td>
<td><p>預設</p></td>
<td><p>商務用 Skype</p></td>
</tr>
<tr class="even">
<td><p>商務用 Skype Server 2015</p></td>
<td><p>對</p></td>
<td><p>商務用 Skype</p></td>
</tr>
<tr class="odd">
<td><p>商務用 Skype Server 2015</p></td>
<td><p>錯</p></td>
<td><p>使用者要求切換至 Lync 模式 (使用者可以在稍後將 UI 設定變更為 $true，以切換至商務用 Skype。) </p></td>
</tr>
<tr class="even">
<td><p>使用正確修補程式的 lync Server 2010 或 Lync Server 2013 () </p></td>
<td><p>預設</p></td>
<td><p>使用者要求切換至 Lync 模式 (使用者可以在稍後將 UI 設定變更為 $true，以切換至商務用 Skype。) </p></td>
</tr>
<tr class="odd">
<td><p>使用正確修補程式的 lync Server 2010 或 Lync Server 2013 () </p></td>
<td><p>對</p></td>
<td><p>商務用 Skype</p></td>
</tr>
<tr class="even">
<td><p>使用正確修補程式的 lync Server 2010 或 Lync Server 2013 () </p></td>
<td><p>錯</p></td>
<td><p>使用者要求切換至 Lync 模式 (使用者可以在稍後將 UI 設定變更為 $true，以切換至商務用 Skype。) </p></td>
</tr>
<tr class="odd">
<td><p>不含修補程式的 lync Server 2010 或 Lync Server 2013 () </p></td>
<td><p>預設</p></td>
<td><p>使用者要求切換至 Lync 用戶端體驗 (使用者無法切換至商務用 Skype) </p></td>
</tr>
</tbody>
</table>


下表顯示管理員變更 Skype 使用者介面體驗的初始設定時，用戶端的經驗。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>伺服器版本</p></th>
<th><p>Skype 使用者介面設定</p></th>
<th><p>用戶端 UI = Lync</p></th>
<th><p>用戶端 UI = 商務用 Skype</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>商務用 Skype Server 2015</p></td>
<td><p>對</p></td>
<td><p>使用者要求切換至商務用 Skype</p></td>
<td><p>商務用 Skype</p></td>
</tr>
<tr class="even">
<td><p>商務用 Skype Server 2015</p></td>
<td><p>錯</p></td>
<td><p>Lync 使用者介面</p></td>
<td><p>使用者要求切換至 Lync UI</p></td>
</tr>
<tr class="odd">
<td><p>使用正確修補程式的 lync Server 2010 或 Lync Server 2013 () </p></td>
<td><p>對</p></td>
<td><p>使用者要求切換至商務用 Skype</p></td>
<td><p>商務用 Skype</p></td>
</tr>
<tr class="even">
<td><p>使用正確修補程式的 lync Server 2010 或 Lync Server 2013 () </p></td>
<td><p>錯</p></td>
<td><p>Lync 使用者介面</p></td>
<td><p>使用者要求切換至 Lync UI</p></td>
</tr>
<tr class="odd">
<td><p>不含修補程式的 lync Server 2010 或 Lync Server 2013 () </p></td>
<td><p>預設</p></td>
<td><p>Lync 模式 (無法切換至商務用 Skype) </p></td>
<td><p>Lync UI (無法切換至商務用 Skype) </p></td>
</tr>
</tbody>
</table>


管理商務用 Skype 用戶端設定所需的修補程式版本如下：

  - Lync Server 2010-2 月2015累積更新 (4.0.7577.710) 的 Lync Server 2010。 如需詳細資訊，請參閱[Lync Server 2010 的更新](https://go.microsoft.com/fwlink/p/?linkid=532771)

  - Lync Server 2013-Lync Server 2013 的2014累計更新 (5.0.8308.857) 。 如需詳細資訊，請參閱[Lync Server 2013 的更新](https://go.microsoft.com/fwlink/p/?linkid=532772)。

</div>

<div>

## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a>建立群組原則物件以在加入網域的電腦上修改登錄

當使用者第一次啟動商務用 Skype 用戶端時，要顯示 Lync 用戶端經驗的登錄更新，應只執行一次。 如果您使用群組原則物件 (GPO) 來更新登錄，您必須定義物件來建立新的值，而不是更新值資料。 套用 GPO 時，如果新值不存在，GPO 將會建立它，並將數值資料設定為0。

下列程式說明如何修改登錄，讓使用者第一次啟動商務用 Skype 時，才會顯示 Lync 用戶端經驗。 您也可以使用此程式來更新登錄，以停用先前所述的歡迎畫面教學課程。

**建立 GPO**

1.  啟動 [**群組原則管理主控台**]。
    
    如需如何使用「群組原則管理主控台」的詳細資訊，請參閱[群組原則管理主控台](https://go.microsoft.com/fwlink/?linkid=532759)。

2.  在 [**群組原則物件**] 節點上按一下滑鼠右鍵，然後在功能表上選取 [**新增**]。

3.  在 [**新增 gpo** ] 對話方塊中，輸入 GPO 的名稱，例如 [ **MakeLyncDefaultUI**]，然後按一下 **[確定]**。

4.  在您剛才建立的新 GPO 上按一下滑鼠右鍵，然後從功能表中選取 [**編輯**]。

5.  在 [**群組原則管理編輯器**] 中，展開 [**使用者**設定]，展開 [**喜好**設定]，展開 [ **Windows 設定**]，然後選取**登錄節點。**

6.  **在 [登錄**] 節點上按一下滑鼠右鍵，然後選取 [**新增**登錄 \> **專案**]。

7.  在 [**新增註冊表屬性**] 對話方塊中，更新下列專案：
    
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>欄位</th>
    <th>要選取或輸入的值</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>動作</strong></p></td>
    <td><p><strong>Create</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>蜂巢</strong></p></td>
    <td><p>HKEY_CURRENT_USER</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>機碼路徑</strong></p></td>
    <td><p>Software\Microsoft\Office\Lync</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Value name</strong></p></td>
    <td><p>EnableSkypeUI</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Value type</strong></p></td>
    <td><p>REG_BINARY</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>值資料</strong></p></td>
    <td><p>00000000</p></td>
    </tr>
    </tbody>
    </table>


8.  按一下 **[確定]** 以儲存變更，然後關閉 GPO。

接下來，您必須將您建立的 GPO 連結至您要指派原則的使用者群組，例如 OU。

**若要使用 GPO 指派原則**

1.  在 [群組原則管理主控台] 中，以滑鼠右鍵按一下您要指派原則的 OU，然後選取 [**連結到現有的 GPO**]。

2.  在 [**選取 gpo** ] 對話方塊中，選取您建立的 GPO，然後選取 **[確定**]。

3.  在目標使用者的電腦上，開啟命令提示字元，並輸入下列命令：
    
    **gpupdate/target： user**
    
    郵件「更新原則 ...」會在應用 GPO 時顯示。 完成後，就會顯示「已成功完成使用者原則更新」郵件。

4.  在命令提示字元處，輸入下列命令：
    
    **gpresult/r**
    
    您應該會看到 "指派的群組原則物件"，具有您在下方所建立的 GPO 名稱。

您也可以檢查登錄，以確認 GPO 是否已成功更新使用者電腦上的登錄。 開啟登錄編輯程式，並流覽至** \[ HKEY \_ 目前的 \_ 使用者 \\ 軟體 \\ Microsoft \\ Office \\ Lync \] **金鑰。 如果 GPO 成功更新登錄，您將會看到名為 EnableSkypeUI 的值，其值為0。

</div>

</div>

<span> </span>

</div>

</div>

</div>

