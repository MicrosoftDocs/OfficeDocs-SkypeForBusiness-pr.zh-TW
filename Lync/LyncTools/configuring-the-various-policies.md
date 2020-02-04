---
title: 設定各種原則
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Configuring the Various Policies
ms:assetid: e3b3cbda-7c17-470b-acb0-82fdcc473184
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945610(v=OCS.15)
ms:contentKeyID: 51541436
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6316a1027de963cefea6c0c76051f09cb5d33538
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727683"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-various-policies"></a>設定各種原則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-24_

<div>

## <a name="configuring-the-various-policies"></a>設定各種原則

以下是您可以在 Lync Server 2013 拓撲中設定的各種原則，在執行 Lync Server 2013 的壓力和效能工具之前。

<div>

## <a name="configuring-the-archiving-policy"></a>設定存檔原則

請參閱範例腳本 ArchivingPolicy. ps1。 只有在您的拓撲中部署了存檔伺服器時，才能使用此腳本。 如需詳細資訊，請參閱 lync server 2013 檔和 Cmdlet[在 Lync server 2013 中的存檔與監控 Cmdlet](https://technet.microsoft.com/en-us/library/gg415629\(v=ocs.15\))說明。

</div>

<div>

## <a name="configuring-the-conferencing-policy"></a>設定會議原則

請參閱範例腳本 MeetingPolicy. ps1。 如需詳細資訊，請參閱 lync server 2013 檔和[Lync server 2013 中的 Web 會議](https://technet.microsoft.com/en-us/library/gg415675\(v=ocs.15\))Cmdlet Cmdlet 說明。

</div>

<div>

## <a name="configuring-the-contacts-policy"></a>設定連絡人原則

請參閱範例 ContactsPolicy. ps1。 如需詳細資訊，請參閱 lync Server 2013 檔和[Lync server 2013 中的 IM 和目前狀態 Cmdlet](https://technet.microsoft.com/en-us/library/gg398611\(v=ocs.15\))的 Cmdlet 說明。

</div>

<div>

## <a name="configuring-the-federation-policy"></a>配置同盟原則

請參閱範例 FederationPolicy. ps1。 如需詳細資訊，請參閱 lync server 2013 檔和 lync server 2013 中的 [lync server 2013] 和 [[同盟與外部存取 Cmdlet](https://technet.microsoft.com/en-us/library/gg415651\(v=ocs.15\))] 中的 [ [Edge 伺服器 Cmdlet](https://technet.microsoft.com/en-us/library/gg415635\(v=ocs.15\)) ] Cmdlet 說明。

</div>

<div>

## <a name="configuring-the-call-admission-control-policy"></a>設定通話許可控制原則

請參閱範例 BandwidthPolicy. ps1。 如需詳細資訊，2013請參閱 lync server [2013 中的通話許可控制](https://technet.microsoft.com/en-us/library/gg398529\(v=ocs.15\))說明，以及[lync Server 2013 中通話許可控制 Cmdlet](https://technet.microsoft.com/en-us/library/gg415676\(v=ocs.15\))的 Cmdlet 說明。

</div>

<div>

## <a name="configuring-the-voice-routing-rules"></a>設定語音路由規則

請參閱範例 RoutingRules. ps1。 當您設定語音路由規則時，請記下手機內容（即/Location 設定檔或/SimpleName）及內部/外部區功能變數代碼，讓您在建立使用者時和 LyncPerfTool 設定期間（特別是 PSTN UC 與 UC）進行指定。 例如，在 RoutingRules. ps1 中，對**CsDialPlan** Cmdlet 的呼叫中的 SimpleName 參數，都應該用於 UserProfileGenerator 下圖中的 LocationProfile 值。

![語音路由規則範例。](images/JJ945610.9f34d971-4ed0-4a4c-b101-086a91c4578c(OCS.15).jpg "語音路由規則範例。")

如需詳細資訊，請參閱 lync server 2013 檔和[Lync server 2013 中企業語音 Cmdlet](https://technet.microsoft.com/en-us/library/gg415658\(v=ocs.15\))的 Cmdlet 說明。

</div>

<div>

## <a name="configuring-conferencing-attendant-application"></a>設定會議助理應用程式

請參閱範例 ConferenceAutoAttendantConfiguration. ps1。 記下 ConferencingAutoAttendant 的電話號碼（預設為1121111111），這樣您就可以將它輸入到 LyncPerf 工具設定工具中，以進行配置產生。

![設定會議服務員應用程式](images/JJ945610.0618a22f-27a9-423a-9085-d2bf71e82db6(OCS.15).jpg "設定會議服務員應用程式")

如需詳細資訊，請參閱 lync server 2013 檔和 lync server 2013 中的[Lync server 2013](https://technet.microsoft.com/en-us/library/gg415675\(v=ocs.15\))和[電話撥入式會議 Cmdlet](https://technet.microsoft.com/en-us/library/gg415630\(v=ocs.15\))中的 Web 會議 Cmdlet Cmdlet 說明。

</div>

<div>

## <a name="configuring-lync-server-call-park-service"></a>正在設定 Lync Server 通話寄存服務

通話駐留預設為停用。 請參閱範例 CallParkConfiguration. ps1。 如需詳細資訊，請參閱 lync server 2013 檔和[Lync server 2013 中通話駐留應用程式 Cmdlet](https://technet.microsoft.com/en-us/library/gg415639\(v=ocs.15\))的 Cmdlet 說明。

</div>

<div>

## <a name="configuring-emergency-calls"></a>設定緊急通話

請執行下列步驟來設定緊急通話的壓力和效能測試。

1.  設定緊急通話的語音路線。 如需設定此語音路由的範例，請參閱 [路由 E911 至 PSTN] 批註下的 RoutingRules 腳本。
    
    <div>
    

    > [!WARNING]  
    > RoutingRules 中的範例命令有一個數位模式，其中包含數位119，而不是911。 您應該避免使用911（或您的實際當地緊急號碼）來避免在負載測試期間意外呼叫本機緊急操作員。 此設定僅供模擬之用。

    
    </div>

2.  您可以在 UserProvisioningTool 中的 [**宏] 索引標籤上填入**值來設定位址，如下圖所示。
    
    ![設定位置資訊服務。](images/JJ945610.8ac1faa1-e9f9-40d0-b8b7-b159f4f459f7(OCS.15).jpg "設定位置資訊服務。")  

3.  按一下 [**產生 .Lis 設定檔**]。

4.  會產生埠、子網、開關和無線存取點（WAPs）的 CSV 檔案，以及 Lync Server 2013 應力和效能工具的 XML 檔案。 當您使用 LisConfiguration. ps1 腳本設定位置資訊服務（.LIS）時，CSV 檔案會當作輸入（在同一個資料夾中）使用。 將產生的 Locations0 檔案移至 Lync Server 2013 應力和效能工具可執行檔（LyncPerfTool）的相同資料夾中，這將會執行位置設定檔（撥號方案）。

</div>

<div>

## <a name="creating-enabling-configuring-and-disabling-users"></a>建立、啟用、設定及停用使用者

在執行下列腳本前，您應該先建立所有的使用者。 依照[建立使用者和連絡人](create-users-and-contacts.md)中的指示來建立使用者。 如需詳細資訊，請參閱適用于[move-csuser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\))、 [Move-csuser](https://technet.microsoft.com/en-us/library/gg398510\(v=ocs.15\))和[Disable move-csuser](https://technet.microsoft.com/en-us/library/gg398747\(v=ocs.15\)) Cmdlet 的 Lync Server 2013 Cmdlet 檔。

</div>

<div>

## <a name="configuring-response-group-application"></a>配置回應群組應用程式

請參閱範例 ResponseGroupConfiguration. ps1。 如需詳細資訊，請參閱 lync server 2013 檔和適用于[Lync server 2013 中之回應群組應用程式 Cmdlet](https://technet.microsoft.com/en-us/library/gg415654\(v=ocs.15\))的 Cmdlet 說明。若要查看回應群組應用程式設定， `https://<poolfqdn>/RgsConfig/`請參閱，如下圖所示。

![回應群組設定工具。](images/JJ945610.480a9440-2283-4533-98f8-86daaab4781c(OCS.15).jpg "回應群組設定工具。")

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

