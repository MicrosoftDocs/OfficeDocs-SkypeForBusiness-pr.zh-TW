---
title: Lync Server 2013：在中繼伺服器上部署 IP 位址類型
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy IP address types on a Mediation Server
ms:assetid: 689ebed5-96ee-4cd4-b7ae-ee2a86a1d9b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204964(v=OCS.15)
ms:contentKeyID: 48184376
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ab30a2153dc7dbf5a15557f6eeaf3b6cb65f68f7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729703"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-ip-address-types-on-a-mediation-server-for-lync-server-2013"></a>針對 Lync Server 2013 在中繼伺服器上部署 IP 位址類型

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016-07-28_

使用拓撲建立器，執行下列程式中的步驟，在中繼伺服器上部署 IP 位址類型。

<div>

## <a name="to-deploy-ip-address-types-on-a-mediation-server"></a>在中繼伺服器上部署 IP 位址類型

  - 在拓撲建立器中，在 [**轉送器池**] 底下，以滑鼠右鍵按一下池中的伺服器，然後選取 [**編輯屬性**]。 （或者，選取伺服器，然後從 [**動作**] 功能表按一下 [**編輯屬性**]。）

  - 在 [**編輯屬性**] 對話方塊中，選取您要設定的 IP 位址類型。 針對雙堆疊設定，請選取 [**啟用 IPv4**並**啟用 IPv6**]，如下圖所示。
    
    **中繼伺服器池的 [編輯屬性] 對話方塊**
    
    ![具有 FQDN 的 [Lync Server 一般內容] 頁面](images/JJ204964.4e650aca-dbff-4a86-b10d-f0162c032539(OCS.15).png "具有 FQDN 的 [Lync Server 一般內容] 頁面")
    
      - **使用所有已設定的 IP 位址**。 如果您想要允許使用電腦上定義的任何 IP 位址，請選取此選項。
        
        <div>
        

        > [!NOTE]  
        > 這是 IP 版本6（IPv6）配置的建議選項。

        
        </div>
    
      - **將服務使用限制在選取的 IP 位址**。 選取此選項以指定要在新伺服器上使用的特定位址。 如果您選取此選項，您必須輸入 [主要 IP 位址] 的值。
    
      - [**主要 IP 位址**]。 輸入一個 IP 位址，伺服器會將它用於除公用交換電話網絡（PSTN）以外的所有通訊。 輸入的 IP 位址必須符合 [選取網址類別型] 的格式。
    
      - **PSTN IP 位址**。 在中繼伺服器是獨立的情況中，定義 PSTN IP 位址。 此位址必須符合所選網址類別型的格式。
        
        <div>
        

        > [!NOTE]  
        > Collocated 中繼伺服器角色不支援安裝其他的網路介面卡（NIC） s 以支援 Lync Server 2013 的 PSTN IP 位址設定。 如需 Lync Server 2013 支援的 NIC 配置的詳細資訊，請參閱<A href="lync-server-2013-server-hardware-platforms.md">Lync server 2013 的伺服器硬體平臺</A>。

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

