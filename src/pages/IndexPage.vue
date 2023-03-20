<template>
  <q-page>
    <div class="data-table q-pa-md">
      <q-table
        :rows="rows"
        :columns="columns"
        row-key="name"
        :rows-per-page-options="[20, 40, 80, 100]"
      >
        <template v-slot:header="props">
          <q-tr :props="props">
            <q-th auto-width />
            <q-th v-for="col in props.cols" :key="col.name" :props="props">
              {{ col.label }}
            </q-th>
          </q-tr>
        </template>

        <template v-slot:body="props">
          <q-tr :props="props">
            <q-td auto-width>
              <q-btn
                size="sm"
                :color="props.expand ? 'red' : 'green'"
                round
                dense
                @click="props.expand = !props.expand"
                :icon="props.expand ? 'lock_open' : 'lock'"
              />
            </q-td>
            <q-td v-for="col in props.cols" :key="col.name" :props="props">
              {{ col.value }}
            </q-td>
          </q-tr>
          <q-tr v-show="props.expand" :props="props">
            <q-td colspan="100%">
              <div class="text-left">
                This is expand slot for row above: {{ props.row.name }}.
              </div>
            </q-td>
          </q-tr>
        </template>
      </q-table>
    </div>
  </q-page>
</template>

<script>
const columns = [
  {
    name: "name",
    required: true,
    label: "Budget Code",
    align: "left",
    field: (row) => row.name,
    format: (val) => `${val}`,
    sortable: true,
  },
  {
    name: "type",
    align: "center",
    label: "Type",
    field: "type",
    sortable: true,
  },
  {
    name: "description",
    label: "Description",
    field: "description",
    sortable: true,
  },
  { name: "gag", label: "GAG", field: "gag", sortable: true },
  { name: "costcentre", label: "Cost Centre", field: "costcentre" },
  { name: "tags", label: "Tags", field: "tags" },
  { name: "fundcodes", label: "Fund Codes", field: "fundcodes" },
  {
    name: "2223",
    label: "2022/23",
    field: "2223",
    sortable: true,
    sort: (a, b) => parseInt(a, 10) - parseInt(b, 10),
  },
  {
    name: "2324",
    label: "2023/24",
    field: "2324",
    sortable: true,
    sort: (a, b) => parseInt(a, 10) - parseInt(b, 10),
  },
  {
    name: "2425",
    label: "2024/25",
    field: "2425",
    sortable: true,
    sort: (a, b) => parseInt(a, 10) - parseInt(b, 10),
  },
  {
    name: "2526",
    label: "2025/26",
    field: "2526",
    sortable: true,
    sort: (a, b) => parseInt(a, 10) - parseInt(b, 10),
  },
  {
    name: "2627",
    label: "2026/27",
    field: "2627",
    sortable: true,
    sort: (a, b) => parseInt(a, 10) - parseInt(b, 10),
  },
];

const rows = [
  {
    name: 510150,
    type: "Income",
    description: "School budget share",
    gag: "EFA: Rates Reimbursement",
    costcentre: "GAGINC",
    tags: "-",
    fundcodes: "-",
    2223: "£1,342,052",
    2324: "£1,432,234",
    2425: "£1,543,234",
    2526: "£1,564,054",
    2627: "£1,765,345",
  },
  {
    name: 510200,
    type: "Income",
    description: "Pupil Premium",
    gag: "EFA: Pupil Premium",
    costcentre: "GAGINC",
    tags: "-",
    fundcodes: "-",
    2223: "£110,123",
    2324: "£115,423",
    2425: "£116,634",
    2526: "£119,162",
    2627: "£123,421",
  },
  {
    name: 510250,
    type: "Income",
    description: "Free school meals",
    gag: "EFA: Universal Infant Free School Meals",
    costcentre: "GAGINC",
    tags: "-",
    fundcodes: "-",
    2223: "£224,550",
    2324: "£227,342",
    2425: "£254,555",
    2526: "£261,134",
    2627: "£277,544",
  },
  {
    name: "510450",
    type: "Income",
    description: "Catch up funding",
    gag: "EFA: Year 7 Catch Up",
    costcentre: "GAGINC",
    tags: "-",
    fundcodes: "-",
    2223: "£14,200",
    2324: "£14,300",
    2425: "£14,400",
    2526: "£14,500",
    2627: "£14,600",
  },
  {
    name: "510500",
    type: "Income",
    description: "Teachers Pay Grant",
    gag: "EFA: Other Factors",
    costcentre: "GAGINC",
    tags: "-",
    fundcodes: "-",
    2223: "£120,630",
    2324: "£121,750",
    2425: "£124,730",
    2526: "£127,123",
    2627: "£129,423",
  },
  {
    name: "520100",
    type: "Income",
    description: "LA SEN Funding",
    gag: "Local Authority: Revenue Income",
    costcentre: "GAGINC",
    tags: "-",
    fundcodes: "-",
    2223: "£1,100,400",
    2324: "£1,300,880",
    2425: "£1,600,700",
    2526: "£1,700,400",
    2627: "£1,800,000",
  },
  {
    name: "656700",
    type: "Expenditure",
    description: "Insurance",
    gag: "Insurance",
    costcentre: "GAGINC",
    tags: "-",
    fundcodes: "-",
    2223: "£27,550",
    2324: "£28,580",
    2425: "£24,220",
    2526: "£29,580",
    2627: "£23,520",
  },
  {
    name: "675100",
    type: "Expenditure",
    description: "Apprenticeship Levy",
    gag: "Staff Costs: Indirect employee expenses",
    costcentre: "GAGINC",
    tags: "-",
    fundcodes: "-",
    2223: "£170,000",
    2324: "£180,000",
    2425: "£195,000",
    2526: "£200,000",
    2627: "£210,000",
  },
  {
    name: "675400",
    type: "Expenditure",
    description: "Travel",
    gag: "Staff Costs: Indirect employee expenses",
    costcentre: "GAGINC",
    tags: "-",
    fundcodes: "-",
    2223: "£12,532",
    2324: "£12,874",
    2425: "£13,625",
    2526: "£15,732",
    2627: "£17,731",
  },
  {
    name: "715100",
    type: "Expenditure",
    description: "Rates",
    gag: "Premises: Rates",
    costcentre: "GAGINC",
    tags: "-",
    fundcodes: "-",
    2223: "£240,783",
    2324: "£260,734",
    2425: "£271,533",
    2526: "£277,773",
    2627: "£283,112",
  },
  {
    name: "720100",
    type: "Expenditure",
    description: "Gas",
    gag: "Other Occupancy Costs",
    costcentre: "GAGINC",
    tags: "-",
    fundcodes: "-",
    2223: "£86,533",
    2324: "£88,754",
    2425: "£89,345",
    2526: "£92,123",
    2627: "£94,534",
  },
  {
    name: "720300",
    type: "Expenditure",
    description: "Electricity",
    gag: "Other Occupancy Costs",
    costcentre: "GAGINC",
    tags: "-",
    fundcodes: "-",
    2223: "£45,112",
    2324: "£48,816",
    2425: "£49,745",
    2526: "£51,125",
    2627: "£52,904",
  },
  {
    name: "730100",
    type: "Expenditure",
    description: "Contract cleaning",
    gag: "Premises: Other Premises",
    costcentre: "GAGINC",
    tags: "-",
    fundcodes: "-",
    2223: "£82,100",
    2324: "£83,400",
    2425: "£84,600",
    2526: "£86,100",
    2627: "£87,350",
  },
  {
    name: "730300",
    type: "Expenditure",
    description: "Window cleaning",
    gag: "Premises: Other Premises",
    costcentre: "GAGINC",
    tags: "-",
    fundcodes: "-",
    2223: "£12,400",
    2324: "£12,700",
    2425: "£12,900",
    2526: "£13,200",
    2627: "£13,700",
  },
  {
    name: "760100",
    type: "Expenditure",
    description: "Grounds maintenance",
    gag: "Premises: Maintenance and Services",
    costcentre: "GAGINC",
    tags: "-",
    fundcodes: "-",
    2223: "£10,000",
    2324: "£11,000",
    2425: "£12,000",
    2526: "£13,000",
    2627: "£14,000",
  },
  {
    name: "810200",
    type: "Expenditure",
    description: "Curriculum support services",
    gag: "Supplies & Services: Educational other (exclude IT)",
    costcentre: "GAGINC",
    tags: "-",
    fundcodes: "-",
    2223: "£73,345",
    2324: "£75,534",
    2425: "£76,125",
    2526: "£77,242",
    2627: "£78,902",
  },
  {
    name: "810200",
    type: "Expenditure",
    description: "Student printing",
    gag: "Supplies & Services: Educational other (exclude IT)",
    costcentre: "GAGINC",
    tags: "-",
    fundcodes: "-",
    2223: "£1,782",
    2324: "£1,876",
    2425: "£1,998",
    2526: "£2,121",
    2627: "£2,422",
  },
  {
    name: "810250",
    type: "Expenditure",
    description: "Learning resources",
    gag: "Supplies & Services: Educational other (exclude IT)",
    costcentre: "GAGINC",
    tags: "-",
    fundcodes: "-",
    2223: "£156,500",
    2324: "£157,800",
    2425: "£158,300",
    2526: "£159,100",
    2627: "£163,200",
  },
  {
    name: "820100",
    type: "Expenditure",
    description: "IT Expenditure",
    gag: "Supplies & Services: Educational IT",
    costcentre: "GAGINC",
    tags: "-",
    fundcodes: "-",
    2223: "£1,240,522",
    2324: "£1,245,355",
    2425: "£1,248,142",
    2526: "£1,251,511",
    2627: "£1,253,866",
  },
  {
    name: "825150",
    type: "Expenditure",
    description: "Music Service",
    gag: "Supplies & Services: Educational other (exclude IT)",
    costcentre: "GAGINC",
    tags: "-",
    fundcodes: "-",
    2223: "£27,640",
    2324: "£28,234",
    2425: "£28,997",
    2526: "£29,142",
    2627: "£29,655",
  },
  {
    name: "825250",
    type: "Expenditure",
    description: "Trips",
    gag: "Supplies & Services: Educational other (exclude IT)",
    costcentre: "GAGINC",
    tags: "-",
    fundcodes: "-",
    2223: "£120,000",
    2324: "£130,000",
    2425: "£140,000",
    2526: "£150,000",
    2627: "£160,000",
  },
  {
    name: "835350",
    type: "Expenditure",
    description: "Telephones",
    gag: "Supplies & Services: Non Educational",
    costcentre: "GAGINC",
    tags: "-",
    fundcodes: "-",
    2223: "£12,000",
    2324: "£12,500",
    2425: "£13,000",
    2526: "£13,500",
    2627: "£14,000",
  },
  {
    name: "845100",
    type: "Expenditure",
    description: "Agency supply staff",
    gag: "Staff Costs: Supply/Agency Teaching Staff",
    costcentre: "GAGINC",
    tags: "-",
    fundcodes: "-",
    2223: "£85,897",
    2324: "£88,235",
    2425: "£89,111",
    2526: "£92,512",
    2627: "£95,222",
  },
  {
    name: "860300",
    type: "Expenditure",
    description: "Accountancy",
    gag: "Governance Costs: Other",
    costcentre: "GAGINC",
    tags: "-",
    fundcodes: "-",
    2223: "£11,000",
    2324: "£11,200",
    2425: "£11,400",
    2526: "£11,600",
    2627: "£11,800",
  },
  {
    name: "872700",
    type: "Expenditure",
    description: "Premises costs",
    gag: "Premises: Other Premises",
    costcentre: "GAGINC",
    tags: "-",
    fundcodes: "-",
    2223: "£120,400",
    2324: "£122,400",
    2425: "£124,400",
    2526: "£126,400",
    2627: "£128,400",
  },
];

export default {
  setup() {
    return {
      columns,
      rows,
    };
  },
};
</script>

<style></style>
