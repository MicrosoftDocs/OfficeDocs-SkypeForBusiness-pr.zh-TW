---
title: 設定各種原則
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Configuring the Various Policies
ms:assetid: e3b3cbda-7c17-470b-acb0-82fdcc473184
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945610(v=OCS.15)
ms:contentKeyID: 51541436
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8270452893e6e2e531eed86d730a1ea4f9f604fc
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755487"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-the-various-policies"></a>設定各種原則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-24_

<div>

## <a name="configuring-the-various-policies"></a>設定各種原則

以下是在執行 Lync Server 2013 壓力和效能工具之前，可在 Lync Server 2013 拓撲中設定的各種原則。

<div>

## <a name="configuring-the-archiving-policy"></a>設定封存原則

請參閱範例腳本 ArchivingPolicy.ps1。 只有當封存伺服器部署在拓撲中時，您才需要使用此腳本。 如需詳細資訊，請參閱 Lync server 2013 檔和 Cmdlet[在 Lync server 2013 中的封存及監控 Cmdlet](https://technet.microsoft.com/library/gg415629\(v=ocs.15\))。

</div>

<div>

## <a name="configuring-the-conferencing-policy"></a>設定會議原則

請參閱範例腳本 MeetingPolicy.ps1。 如需詳細資訊，請參閱 lync server 2013 中的 Lync Server 2013 檔和 Cmdlet 說明（ [Web 會議 Cmdlet](https://technet.microsoft.com/library/gg415675\(v=ocs.15\))）。

</div>

<div>

## <a name="configuring-the-contacts-policy"></a>設定連絡人原則

請參閱範例 ContactsPolicy.ps1。 如需詳細資訊，請參閱 Lync server 2013 檔以及[Lync server 2013 中的 IM 和目前狀態 Cmdlet](https://technet.microsoft.com/library/gg398611\(v=ocs.15\))的 Cmdlet 說明。

</div>

<div>

## <a name="configuring-the-federation-policy"></a>設定同盟原則

請參閱範例 FederationPolicy.ps1。 如需詳細資訊，請參閱 lync server [2013 中的 Edge server Cmdlet](https://technet.microsoft.com/library/gg415635\(v=ocs.15\))的 lync server 2013 檔和 Cmdlet 說明，以及[lync server 2013 中的同盟與外部訪問 Cmdlet](https://technet.microsoft.com/library/gg415651\(v=ocs.15\))。

</div>

<div>

## <a name="configuring-the-call-admission-control-policy"></a>設定通話許可控制原則

請參閱範例 BandwidthPolicy.ps1。 如需詳細資訊，請參閱 lync server [2013 中通話許可控制](https://technet.microsoft.com/library/gg398529\(v=ocs.15\))的 [lync server 2013] 檔概述，以及[lync Server 2013 中通話許可控制 Cmdlet](https://technet.microsoft.com/library/gg415676\(v=ocs.15\))的 Cmdlet 說明。

</div>

<div>

## <a name="configuring-the-voice-routing-rules"></a>設定語音路由規則

請參閱範例 RoutingRules.ps1。 當您設定語音路由規則時，請記下電話內容（也就是/Location 設定檔或/SimpleName）和內部/外部區功能變數代碼，這樣您就可以在建立使用者時和 LyncPerfTool 設定期間（特別是針對 PSTN UC 和 UC-PSTN）進行指定。 例如，在 RoutingRules.ps1 範例中對**get-csdialplan 指令程式**的呼叫中，SimpleName 參數應該用於 UserProfileGenerator.exe 的下圖中的 microsoft.rtc.management.writableconfig.policy.voice.locationprofile 值。

![語音路由規則範例。](images/JJ945610.9f34d971-4ed0-4a4c-b101-086a91c4578c(OCS.15).jpg "語音路由規則範例。")

如需詳細資訊，請參閱 lync server 2013 中的 [Lync Server 2013] 檔和 [Cmdlet 說明][中的 Enterprise Voice Cmdlet](https://technet.microsoft.com/library/gg415658\(v=ocs.15\))。

</div>

<div>

## <a name="configuring-conferencing-attendant-application"></a>設定會議助理應用程式

請參閱範例 ConferenceAutoAttendantConfiguration.ps1。 記下 ConferencingAutoAttendant 的電話號碼（預設值為1121111111），讓您可以將它輸入到 LyncPerf 工具設定工具中，以進行設定產生。

![設定會議助理應用程式](images/JJ945610.0618a22f-27a9-423a-9085-d2bf71e82db6(OCS.15).jpg "設定會議助理應用程式")

如需詳細資訊，請參閱 lync server 2013 和 lync server 2013 中的 Lync server 2013 和[電話撥入式會議 Cmdlet](https://technet.microsoft.com/library/gg415630\(v=ocs.15\))[中的 Web 會議 Cmdlet](https://technet.microsoft.com/library/gg415675\(v=ocs.15\))的 Lync server 檔和 Cmdlet 說明。

</div>

<div>

## <a name="configuring-lync-server-call-park-service"></a>設定 Lync Server 通話駐留服務

通話駐留預設為停用。 請參閱範例 CallParkConfiguration.ps1。 如需詳細資訊，請參閱 Lync server 2013 檔和 Cmdlet Help for the [Lync server 2013 中的通話駐留應用程式 Cmdlet](https://technet.microsoft.com/library/gg415639\(v=ocs.15\))。

</div>

<div>

## <a name="configuring-emergency-calls"></a>設定緊急通話

執行下列步驟，為緊急通話設定壓力和效能測試。

1.  設定緊急通話的語音路由。 如需設定這個語音路由的範例，請參閱批註「Route E911 to PSTN」下的 RoutingRules.ps1 腳本。
    
    <div>
    

    > [!WARNING]  
    > RoutingRules.ps1 的範例命令具有數位模式，其中包含數位119，而不是911。 您應避免使用911（或實際的本機緊急號碼），以避免在負載測試期間意外呼叫本機緊急操作員。 此設定僅供類比之用。

    
    </div>

2.  填寫 UserProvisioningTool 中的 [所有 **.lis** ] 索引標籤上的值以設定位址，如下圖所示。
    
    ![設定位置資訊服務。](images/JJ945610.8ac1faa1-e9f9-40d0-b8b7-b159f4f459f7(OCS.15).jpg "設定位置資訊服務。")  

3.  按一下 [**產生 .lis 的設定檔**]。

4.  會產生埠、子網、交換器和無線存取點（Wap）的 CSV 檔案，以及 Lync Server 2013 壓力和效能工具的 XML 檔案。 使用 LisConfiguration.ps1 腳本設定位置資訊服務（.LIS）時，會使用 CSV 檔案作為輸入（位於相同的資料夾中）。 將產生的 Locations0.xml 檔案移至與 Lync Server 2013 應力和效能工具可執行檔（LyncPerfTool.exe）相同的資料夾中，以執行位置設定檔（撥號對應表）案例。

</div>

<div>

## <a name="creating-enabling-configuring-and-disabling-users"></a>建立、啟用、設定及停用使用者

在執行下列腳本之前，您應該先建立所有使用者。 依照[建立使用者和連絡人](create-users-and-contacts.md)以建立使用者的指示進行。 如需詳細資訊，請參閱 Lync Server 2013 Cmdlet 檔，以取得[Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\))、 [Set-CsUser](https://technet.microsoft.com/library/gg398510\(v=ocs.15\))和[get-csuser](https://technet.microsoft.com/library/gg398747\(v=ocs.15\)) Cmdlet。

</div>

<div>

## <a name="configuring-response-group-application"></a>設定回應群組應用程式

請參閱範例 ResponseGroupConfiguration.ps1。 如需詳細資訊，請參閱 Lync server 2013 檔和 Cmdlet 說明，以瞭解[Lync server 2013 中的回應群組應用程式 Cmdlet](https://technet.microsoft.com/library/gg415654\(v=ocs.15\))。若要複查回應群組應用程式設定，請參閱 `https://<poolfqdn>/RgsConfig/` ，如下圖所示。

![回應群組設定工具。](images/JJ945610.480a9440-2283-4533-98f8-86daaab4781c(OCS.15).jpg "回應群組設定工具。")

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

