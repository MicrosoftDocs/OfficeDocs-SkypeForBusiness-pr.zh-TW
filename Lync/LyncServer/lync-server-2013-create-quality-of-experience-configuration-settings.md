---
title: Lync Server 2013：建立體驗品質設定設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create Quality of Experience configuration settings
ms:assetid: 64f05569-07c7-4f76-a96b-ea4125a510d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521006(v=OCS.15)
ms:contentKeyID: 48184357
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 947fb50c057fdcc04fe7d1b30d25bc8f5a5f4a02
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981732"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-quality-of-experience-configuration-settings-in-lync-server-2013"></a>在 Lync Server 2013 中建立體驗配置設定的品質

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

經驗品質（QoE）度量單位會追蹤您組織中的音訊和視頻通話品質，包括網路資料包遺失、背景雜色及「抖動」（資料包延遲的差異）的數量。 這些度量單位會與其他資料（例如通話明細記錄）之外，儲存在資料庫中，讓您可以啟用和停用與其他資料錄製無關的 QoE。

當您安裝 Microsoft Lync Server 2013 時，系統會為您建立單一、全域的 QoE 配置設定集合。 系統管理員也可以選擇在網站範圍中建立自訂設定。 只要使用這些網站範圍的設定，就會優先于全域設定。 例如，如果您為雷德蒙的網站建立網站範圍的設定，則這些設定（而不是 [全域設定]）將會用於管理雷德蒙的 QoE。

您可以使用 Lync Server [控制台] 或[新的-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) Cmdlet 來建立 QoE 設定設定。 如果您使用的是 Lync Server [控制台] 來建立新設定，您會看到下列選項：


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>UI 設定</th>
<th>PowerShell 參數</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>名稱</p></td>
<td><p>Identity</p></td>
<td><p>要建立之設定的唯一識別碼。 QoE 設定只能在網站範圍建立。</p></td>
</tr>
<tr class="even">
<td><p>啟用監視 QoE 資料</p></td>
<td><p>EnableQoE</p></td>
<td><p>指定是否要收集 QoE 記錄並將它儲存到監視資料庫。</p></td>
</tr>
<tr class="odd">
<td><p>啟用清除 QoE 資料</p></td>
<td><p>EnablePurging</p></td>
<td><p>指定是否要在 [保留 QoE 資料] 中定義的持續時間<strong>（天數）</strong>屬性已過久之後，才清除記錄。</p></td>
</tr>
<tr class="even">
<td><p>保留 QoE 資料以取得最長持續時間（天）</p></td>
<td><p>KeepQoEDataForDays</p></td>
<td><p>從資料庫清除 QoE 資料前要儲存的天數。 如果停用清除功能，就會忽略這個值。</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> CsQoEConfiguration Cmdlet 包含無法在 Lync Server [控制台] 中使用的其他選項。 如需詳細資訊，請參閱<A href="https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration">新的 CsQoEConfiguration</A>說明主題。



</div>

<div>

## <a name="to-create-qoe-configuration-settings-by-using-lync-server-control-panel"></a>使用 Lync Server [控制台] 建立 QoE 配置設定

1.  以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。 如需詳細資訊，請參閱[Lync Server 2013 中的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**監視及**封存]，然後按一下 [**體驗資料品質**]。

4.  在 [**體驗品質資料**] 頁面上，按一下 [**新增**]。

5.  在 [**選取網站**] 中，按一下要套用原則的網站，然後按一下 **[確定]**。

6.  在 [**新的體驗品質] 設定**中，請執行下列動作：
    
      - 選取 [**啟用 QoE 資料監視**] 來開啟監視。
    
      - 選取 [**啟用清除 QoE 資料**] 以開啟 [清除]。
    
      - 在 **[保留 QoE 的最大持續時間（天）**] 中，選取 QoE 記錄應保留的最大天數。

7.  按一下 [認可]****。

</div>

<div>

## <a name="creating-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 建立 QoE 配置設定

您可以使用 Windows PowerShell 和 CsQoEConfiguration Cmdlet 來建立 QoE 配置設定。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 遠端會話中執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-create-a-new-collection-of-qoe-configuration-settings"></a>若要建立新的 QoE 配置設定集合

  - 這個命令會建立套用至雷德蒙網站之 QoE 設定設定的新集合：
    
        New-CsQoEConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-collection-of-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a>若要在停用 QoE 監視的情況下，建立新的 QoE 配置設定集合

  - 因為在上述命令中沒有指定任何參數（強制身分識別參數以外），所以新的配置設定集合會將預設值用於其所有屬性。 若要建立使用不同屬性值的設定，只要包含適當的參數和參數值即可。 例如，若要建立經驗品質設定的集合，請根據預設，允許停用 QoE 錄製使用如下所示的命令：
    
        New-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-qoe-configuration-settings"></a>建立新的 QoE 配置設定集合時，指定多個屬性值

  - 您可以加入多個參數，以使用多個屬性值。 例如，這個命令會將新設定設為保留30天的 QoE 資料，並在 3:00 AM 清除舊資料：
    
        New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 30 -PurgeHourOfDay 3

</div>

如需詳細資訊，請參閱[新版-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) Cmdlet 的說明主題。

</div>

</div>

<span> </span>

</div>

</div>

</div>

