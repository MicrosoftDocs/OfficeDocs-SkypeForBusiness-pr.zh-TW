---
title: Lync Server 2013：設定自訂顯示狀態
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring custom presence states
ms:assetid: e17364a8-8b93-45fc-a614-c80e45435d42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398997(v=OCS.15)
ms:contentKeyID: 48185534
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd551ede7d7be7e631c229e99613cfc8baa006eb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526990"
---
# <a name="configuring-custom-presence-states-in-lync-server-2013"></a>在 Lync Server 2013 中設定自訂的顯示狀態

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-01-10_

若要在 Lync 2013 中定義自訂的顯示狀態，請建立 XML 自訂的顯示設定檔，然後使用 Lync Server 管理命令介面 Cmdlet **New-CSClientPolicy** 或 **Set-CSClientPolicy** 參數 CustomStateURL 來指定其位置。

設定檔具有下列屬性：

  - 您可以使用 [可用、忙碌] 和 [請勿打擾] 顯示狀態指標來設定自訂顯示狀態。

  - Availability 屬性決定與自訂狀態的狀態文字相關聯的目前狀態指示器。 在本主題稍後的範例中，會在綠色 (可用) 顯示狀態指示器的右側顯示「住宅工作」的狀態文字。

  - 狀態文字的最大長度為64個字元。

  - 最多可新增四個自訂的顯示狀態。

  - CustomStateURL 參數會指定設定檔的位置。 在 Lync 2013 中，SIP 高安全性模式預設為啟用，因此您需要將自訂目前狀態設定檔儲存在已啟用 HTTPS 的網頁伺服器上。 否則，Lync 2013 用戶端將無法與其連線。 例如，有效的位址是 `https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml` 。

<div>


> [!NOTE]  
> 雖然在實際執行環境中不建議使用此方法，但您可以在非 HTTPS 檔案共用上測試組態檔，方法是使用 EnableSIPHighSecurityMode 登錄設定，以停用用戶端的 SIP 高安全性模式。 然後，您可以使用 CustomStateURL 登錄設定來指定設定檔的非 HTTPS 位置。 請注意，Lync 2013 會考慮 Lync 2010 登錄設定，但是登錄蜂巢已更新。 您可以建立登錄設定，如下所示： 
> <UL>
> <LI>
> <P>HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\EnableSIPHighSecurityMode</P>
> <P>類型：DWORD</P>
> <P>值資料：0</P>
> <LI>
> <P>HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\CustomStateURL</P>
> <P>Type： String (REG_SZ) </P>
> <P>數值資料 (範例) ： file:// \\lspool.corp.contoso.com\LSFileShare\ClientConfigFolder\Presence.xml 或 file:///c:/LSFileShare/ClientConfigFolder/Group_1_Pres.xml</P></LI></UL>



</div>

在 XML 設定檔中，指定一或多個地區識別碼 (LCID) 架構，以當地語系化您的自訂狀態狀態。 本主題稍後的範例會在 1033) 、挪威文（博克瑪律性） (1044) 中，French-France (1036) ，以及土耳其文 (1055) ，將當地語系化展示為英文的美國 ( 如需 Lcid 的清單，請參閱由 Microsoft 所指派的地區設定 IDs <https://go.microsoft.com/fwlink/p/?linkid=157331> 。

<div>

## <a name="to-add-custom-presence-states-to-lync-2013"></a>若要將自訂目前狀態新增至 Lync 2013

1.  建立使用下列範例格式的 XML 設定檔：
    
        <?xml version="1.0"?>
        <customStates xmlns="http://schemas.microsoft.com/09/2009/communicator/customStates">
          <customState ID="1" availability="online">
            <activity LCID="1033">Working from Home</activity>
            <activity LCID="1044">activity 2 for 1044</activity>
            <activity LCID="1055">activity 3 for 1055</activity>
          </customState>
          <customState ID="2" availability="busy">
            <activity LCID="1033">In a Live Meeting</activity>
            <activity LCID="1036">Equivalent French String for - In a Live Meeting </activity>
          </customState>
          <customState ID="3" availability="busy">
            <activity LCID="1033">Meeting with Customer</activity>
            <activity LCID="1055">meeting with client</activity>
            <activity LCID="1036">Equivalent French String for - Meeting with Customer</activity>
          </customState>
          <customState ID="4" availability="do-not-disturb">
            <activity LCID="1033">Interviewing</activity>
          </customState>
        </customStates>

2.  將 XML 設定檔儲存到啟用 HTTPS 的網頁伺服器。 在此範例中，會將檔案命名為 Presence.xml，並將其儲存至該位置 https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml 。

3.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

4.  在 Lync Server 管理命令介面中，使用類似下列的命令，定義 XML 設定檔的位置：
    
        New-CsClientPolicy -Identity ContosoCustomStates 
        -CustomStateURL "https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml"

5.  使用 **Grant-CSClientPolicy** Cmdlet 將此新原則指派給使用者。

如需詳細資訊，請參閱 Lync Server 管理命令介面檔中的 [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) 和 [Grant-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsClientPolicy) 。

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>Lync Server 2013 預設會 &nbsp; 每三個小時更新一次用戶端原則和設定。</P>
> <LI>
> <P>如果您想要繼續使用舊版本的群組原則設定，例如 CustomStateURL，當 Lync 2013 位於新原則登錄蜂巢 ( # A0 時，將會辨識設定。 不過，以伺服器為基礎的用戶端原則會優先。</P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

