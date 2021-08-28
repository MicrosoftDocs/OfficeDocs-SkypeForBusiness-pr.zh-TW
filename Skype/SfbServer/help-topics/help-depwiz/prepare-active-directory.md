---
title: 準備 Active Directory
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainADPrep
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: a8c96311-9e1c-4d39-9870-681fd4e272ff
description: 若要開始安裝商務用 Skype Server 2015，您必須準備要主控伺服器和使用者之 Active Directory 網域服務架構、樹系和網域。 商務用 Skype Server 部署嚮導會引導您逐步完成準備 Active Directory 的步驟（從架構開始，然後再到樹系準備）。 確認 Active Directory 複寫成功後，您就可以準備要主控使用者或伺服器的每個網域。
ms.openlocfilehash: 1a50936858c2a6d40b92fca3c5fc6e6663a00bb3
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58602828"
---
# <a name="prepare-active-directory"></a>準備 Active Directory

若要開始安裝商務用 Skype Server 2015，您必須準備要主控伺服器和使用者之 Active Directory 網域服務架構、樹系和網域。 商務用 Skype Server 部署嚮導會引導您逐步完成準備 Active Directory 的步驟（從架構開始，然後再到樹系準備）。 確認 Active Directory 複寫成功後，您就可以準備要主控使用者或伺服器的每個網域。

> [!IMPORTANT]
> 若要順利準備架構，您必須以 Enterprise Admins 群組和 schema Admins 群組成員的身分登入。 若要準備樹系，您必須以 Enterprise Admins 群組成員的身分登入，或以樹系根管理員的身分登入。 若要進行網域準備，您必須以 Domain Admins 群組成員的身分登入。

如需支援的 Active Directory 拓撲的詳細資訊，請參閱支援檔中的 [Active Directory 支援](/previous-versions/office/lync-server-2013/lync-server-2013-active-directory-support) 。 如需 Active Directory 準備的詳細資訊，請參閱部署檔中的 [Active Directory 網域服務準備工作](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-active-directory-domain-services-preparation) 。