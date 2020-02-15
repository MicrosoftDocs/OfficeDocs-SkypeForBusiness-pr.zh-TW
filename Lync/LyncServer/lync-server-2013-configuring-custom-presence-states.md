---
title: Lync Server 2013： 設定自訂目前狀態
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
ms.openlocfilehash: 75e2e47af4951e98f21ea6b26572d39b5eebcb8d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046476"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-custom-presence-states-in-lync-server-2013"></a>在 Lync Server 2013 中設定自訂目前狀態

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-01-10_

若要在 Lync 2013 中定義自訂目前狀態，建立 XML 自訂目前狀態設定檔，並接著藉由使用 Lync Server 管理命令介面 cmdlet **New-csclientpolicy**或**Set-csclientpolicy**搭配參數 customstateurl 來指定其位置。

設定檔包含下列屬性：

  - 可以使用適用於 」、 「 忙碌 」 和 「 請勿打擾顯示狀態指示器來設定自訂目前狀態。

  - 可用性屬性會決定關聯的自訂狀態的狀態文字的顯示狀態指示器。 在本主題稍後的範例中，狀態文字在家工作會顯示綠色 （線上） 顯示狀態指示器的右邊。

  - 狀態文字的長度上限是 64 個字元。

  - 可以新增最多四個自訂目前狀態。

  - CustomStateURL 參數指定的組態檔的位置。 在 Lync 2013 中，SIP 高安全性模式預設會啟用，因此您需要儲存網頁伺服器已啟用 HTTPS 上的自訂目前狀態設定檔。 否則，Lync 2013 用戶端將無法連線到它。 例如，就是有效的地址`https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml`。

<div>


> [!NOTE]  
> 雖然不建議在生產環境中，您可以測試的組態檔，位於非 HTTPS 檔案共用上使用 EnableSIPHighSecurityMode 登錄設定，停用用戶端上的 SIP 高安全性模式。 然後您可以使用 customstateurl 來登錄設定來指定的組態檔的非 HTTPS 位置。 請注意，Lync 2013 接受 Lync 2010 登錄設定，但已更新登錄區。 您可以建立的登錄設定，如下所示： 
> <UL>
> <LI>
> <P>HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\EnableSIPHighSecurityMode</P>
> <P>類型： DWORD</P>
> <P>數值資料： 0</P>
> <LI>
> <P>HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\CustomStateURL</P>
> <P>類型： 字串 (REG_SZ)</P>
> <P>數值資料 （範例）： file://\\lspool.corp.contoso.com\LSFileShare\ClientConfigFolder\Presence.xml 或 file:///c:/LSFileShare/ClientConfigFolder/Group_1_Pres.xml</P></LI></UL>



</div>

XML 設定檔，以指定一或多個地區設定識別碼 (LCID) 結構描述當地語系化您自訂目前狀態。 稍後在這個範例主題會顯示成英文-當地語系化 United States (1033)、 挪威文-巴克摩 (1044)、 法文-法國 (1036) 及土耳其文 (1055)。 Lcid 的清單，請參閱在 microsoft 指派的地區識別碼<http://go.microsoft.com/fwlink/p/?linkid=157331>。

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

2.  儲存至網頁伺服器的 XML 設定檔，以啟用 HTTPS。 在這個範例中，該檔案是名為 Presence.xml 和儲存位置， https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml。

3.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

4.  在 Lync Server 管理命令介面，定義在 XML 設定檔的位置使用類似下列的命令：
    
        New-CsClientPolicy -Identity ContosoCustomStates 
        -CustomStateURL "https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml"

5.  使用**Grant-csclientpolicy** cmdlet 將此新原則指派給使用者。

如需詳細資訊，請參閱 Lync Server 管理命令介面文件中的[New-csclientpolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy)和[Grant-csclientpolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsClientPolicy) 。

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>根據預設，Lync Server 2013&nbsp;每三小時更新用戶端原則和設定。</P>
> <LI>
> <P>如果您想要繼續使用群組原則設定，從先前的版本，例如 CustomStateURL、 Lync 2013 會辨識設定，如果他們位於中新的原則登錄區 (HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync)。 不過，伺服器為基礎的用戶端原則的優先順序。</P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

