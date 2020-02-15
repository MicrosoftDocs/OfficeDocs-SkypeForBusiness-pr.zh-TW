---
title: 設定服務品質原則的 A / V Edge Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a Quality of Service policy for your A/V Edge Servers
ms:assetid: 119ee1f5-45b9-40ba-98e5-c694dd2fc5c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204681(v=OCS.15)
ms:contentKeyID: 48183444
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e55947fa80e2772bbc53b47f5c6f906761f1bb3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034213"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-quality-of-service-policy-for-your-av-edge-servers-in-lync-server-2013"></a>設定服務品質原則的 A / V Edge Servers in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-19_

除了為會議伺服器、應用程式伺服器及中繼伺服器建立 QoS 原則，您也必須為 A/V Edge Server 的內部端建立音訊及視訊原則。不過，在 Edge Server 上使用的原則，不同於在會議伺服器、應用程式伺服器及中繼伺服器上使用的原則。針對會議伺服器、應用程式伺服器及中繼伺服器，您會指定來源連接埠範圍；針對 Edge Server，則需要指定目的連接埠範圍。因此，您不能直接將會議伺服器、應用程式伺服器及中繼伺服器 QoS 原則套用至 Edge Server：這些原則就是不會作用。反之，您必須建立新的原則，並將這些原則只套用到 Edge Server。

下列程序說明如何在 Edge Server 上，建立可以用來管理服務品質的 Active Directory 群組原則物件。當然，您的 Edge Server 有可能是沒有 Active Directory 帳戶的獨立伺服器。若是如此，您可以使用本機群組原則來代替 Active Directory 群組原則：唯一不同的是，您必須使用本機群組原則編輯器來建立這些本機原則，而且必須在每部 Edge Server 上個別建立相同的原則集。若要在 Edge Server 上啟動本機群組原則編輯器，請執行下列動作：

1.  按一下 [開始]****，然後按一下 [執行]****。

2.  在 [執行]**** 對話方塊中，輸入 **gpedit.msc**，然後按 ENTER。

如果您要建立 Active Directory 型原則，應登入已安裝群組原則管理的電腦。之後，開啟群組原則管理 (按一下 [開始]****，指向 [系統管理工具]****，然後按一下 [群組原則管理]****)，接著完成下列步驟：

1.  在群組原則管理中，找出要用來建立新原則的容器。例如，如果您的所有 Lync Server 電腦都位在名為 Lync Server 的 OU 中，則新原則應建立在 Lync Server OU 中。

2.  以滑鼠右鍵按一下適當的容器，然後按一下 [在這個網域中建立 GPO 並連結到]****。

3.  在 [新增 GPO]**** 對話方塊的 [名稱]**** 方塊中，輸入新群組原則物件的名稱 (例如，**Lync Server Audio**) ，然後按一下 [確定]****。

4.  以滑鼠右鍵按一下新建的原則 ，然後按一下 [編輯]****。

從這裡開始，無論您是要建立 Active Directory 原則或本機原則，程序都一樣：

1.  在群組原則管理編輯器或本機群組原則編輯器中，依序展開 [電腦設定]****、[原則]****、[Windows 設定]****，以滑鼠右鍵按一下 [以原則為依據的 QoS]****，然後按一下 [建立新原則]****。

2.  在 [以原則為依據的 QoS]**** 對話方塊中，於開啟頁面上的 [名稱]**** 方塊中輸入新原則的名稱 (例如，**Lync Server Audio**)。選取 [指定 DSCP 數值]****，並將該值設為 **46**。將 [指定輸出節流閥速率]**** 保留未選取狀態，然後按 [下一步]****。

3.  在下一頁上，確定已選取 [所有應用程式]****，然後按 [下一步]****。此設定會指示網路尋找 DSCP 標示為 46 的所有封包，而不只是特定應用程式建立的封包。

4.  在第三頁上，確定 [任何來源 IP 位址]**** 及 [任何目的地 IP 位址]**** 都已選取，然後按 [下一步]****。這兩個設定可確保無論是哪部電腦 (IP 位址) 傳送封包，以及哪部電腦 (IP 位址) 接收封包，那些封包都會受到管理。

5.  在第四頁上，從 [選取此 QoS 原則套用的通訊協定]**** 下拉式清單中選取 [TCP 及 UDP]****。 （傳輸控制通訊協定） TCP 及 UDP （使用者資料包通訊協定） 是最常使用的 Lync Server 和其用戶端應用程式的兩個網路通訊協定。

6.  在 [指定目的地連接埠號碼]**** 標題底下，選取 [從此目的地連接埠或範圍]****。在隨附的文字方塊中，輸入為音訊傳輸保留的連接埠範圍。例如，如果您為音訊傳輸保留連接埠 49152 到 57500，則使用下列格式來輸入連接埠範圍：**49152:57500**。按一下 [完成]****。

在為音訊傳輸建立 QoS 原則之後，應為視訊傳輸建立第二個原則。若要為視訊建立原則，請遵循您建立音訊原則時所使用的相同基本程序，並替換下列項目：

  - 使用不同的 (且唯一的) 原則名稱 (例如，**Lync Server Video**)。

  - 將 DSCP 值設為 **34** 而不是 46。(請注意，DSCP 值不一定要使用 34。唯一的要求是用於視訊和音訊的 DSCP 值必須不同。)

  - 為視訊傳輸使用先前設定的連接埠範圍。例如，如果您已為視訊保留連接埠 57501 到 65535，則將連接埠範圍設為：**57501:65535**。再強調一次，這應該設為目的地連接埠範圍。

如果您決定建立原則來管理應用程式共用流量，則必須建立第三原則，請替換下列項目：

  - 使用不同的 (且唯一的) 原則名稱 (例如，**Lync Server Application Sharing**)。

  - 將 DSCP 值設為 **24** 而不是 46。(再強調一次，DSCP 值不一定要使用 24。唯一的要求是用於應用程式共用的 DSCP 值必須與視訊或音訊不同。)

  - 為視訊傳輸使用先前設定的連接埠範圍。例如，如果您已為應用程式共用保留連接埠 40803 到 49151，則將連接埠範圍設為：**40803:49151**。

必須在 Edge Server 上重新整理群組原則之後，您建立的新原則才會生效。雖然群組原則本身會定期重新整理，但您可以在需要重新整理群組原則的每部電腦上執行下列命令，以強制立即重新整理：

    Gpudate.exe /force

在 Lync Server 或從任何命令視窗中，執行系統管理員認證，可以從執行此命令。 若要以系統管理員憑證執行命令視窗，請按一下 [開始]****，以滑鼠右鍵按一下 [命令提示字元]****，然後按一下 [以系統管理員身分執行]****。 請注意，即使在執行 Gpudate.exe 之後，可能還是需要重新啟動 Edge Server。

為幫助確保網路封包標示適當的 DSCP 值，您也應該要在每部電腦上建立新的登錄項目，請完成下列程序：

1.  按一下 [開始]****，然後按一下 [執行]****。

2.  在 [執行]**** 對話方塊中，輸入 **regedit**，然後按 ENTER。

3.  在登錄編輯程式中，依序展開 [ **HKEY\_本機\_機器**、 展開 [**系統**、 [ **CurrentControlSet**、 展開 [**服務**] 及 [ **tcpip]**。

4.  以滑鼠右鍵按一下 [Tcpip]****，指向 [新增]****，然後按一下 [索引鍵]****。建立新的登錄機碼之後，輸入 **QoS**，然後按 ENTER 鍵，以將索引鍵重新命名。

5.  以滑鼠右鍵按一下 [QoS]****，指向 [新增]****，然後按一下 [字串值]****。建立新的登錄值之後，輸入 **Do not use NLA**，然後按 ENTER 鍵，以將該值重新命名。

6.  按兩下 [Do not use NLA]****。在 [編輯字串]**** 對話方塊的 [數值資料]**** 方塊中輸入 **1**，然後按一下 [確定]****。

7.  關閉登錄編輯程式，然後重新啟動電腦。

</div>

<span> </span>

</div>

</div>

</div>

