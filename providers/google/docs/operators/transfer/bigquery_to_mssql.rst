 .. Licensed to the Apache Software Foundation (ASF) under one
    or more contributor license agreements.  See the NOTICE file
    distributed with this work for additional information
    regarding copyright ownership.  The ASF licenses this file
    to you under the Apache License, Version 2.0 (the
    "License"); you may not use this file except in compliance
    with the License.  You may obtain a copy of the License at

 ..   http://www.apache.org/licenses/LICENSE-2.0

 .. Unless required by applicable law or agreed to in writing,
    software distributed under the License is distributed on an
    "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
    KIND, either express or implied.  See the License for the
    specific language governing permissions and limitations
    under the License.


Google Cloud BigQuery Transfer Operator to Microsoft SQL Server
===============================================================

`Google Cloud BigQuery <https://cloud.google.com/bigquery>`__ is Google Cloud's serverless
data warehouse offering.
`Microsoft SQL Server (MsSQL) <https://www.microsoft.com/en-us/sql-server/sql-server-2019>`__
is a relational database management system developed by Microsoft.
This operator can be used to copy data from a BigQuery table to MSSQL.


Prerequisite Tasks
^^^^^^^^^^^^^^^^^^

.. include:: /operators/_partials/prerequisite_tasks.rst

.. _howto/operator:BigQueryToMsSqlOperator:

Operator
^^^^^^^^

Copying data from one BigQuery table to another is performed with the
:class:`~airflow.providers.google.cloud.transfers.bigquery_to_mssql.BigQueryToMsSqlOperator` operator.

Use :ref:`Jinja templating <concepts:jinja-templating>` with
:template-fields:`airflow.providers.google.cloud.transfers.bigquery_to_mssql.BigQueryToMsSqlOperator`
to define values dynamically.

You may use the parameter ``selected_fields`` to limit the fields to be copied (all fields by default),
as well as the parameter ``replace`` to overwrite the destination table instead of appending to it.
For more information, please refer to the links above.


Transferring data
-----------------

The following Operator copies data from a BigQuery table to MsSQL.

.. exampleinclude:: /../../google/tests/system/google/cloud/bigquery/example_bigquery_to_mssql.py
    :language: python
    :dedent: 4
    :start-after: [START howto_operator_bigquery_to_mssql]
    :end-before: [END howto_operator_bigquery_to_mssql]


Reference
^^^^^^^^^

For further information, look at:

* `Google Cloud BigQuery Documentation <https://cloud.google.com/bigquery/docs/>`__
* `Microsoft SQL Server Documentation <https://docs.microsoft.com/en-us/sql/?view=sql-server-ver15>`__
