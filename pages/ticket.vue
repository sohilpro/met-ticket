<template>
  <section class="mx-5 my-5">
    <button
      :disabled="loading"
      @click="downloadPdf"
      class="bg-blue-500 text-white px-5 flex gap-2 transition-all py-3 rounded-lg mb-5"
      :class="{ 'opacity-50': loading }"
    >
      Receive tickets as PDF
      <svg
        v-if="loading"
        xmlns="http://www.w3.org/2000/svg"
        width="1.5rem"
        height="1.5rem"
        viewBox="0 0 24 24"
      >
        <path
          fill="currentColor"
          d="M12,1A11,11,0,1,0,23,12,11,11,0,0,0,12,1Zm0,19a8,8,0,1,1,8-8A8,8,0,0,1,12,20Z"
          opacity="0.25"
        />
        <path
          fill="currentColor"
          d="M12,4a8,8,0,0,1,7.89,6.7A1.53,1.53,0,0,0,21.38,12h0a1.5,1.5,0,0,0,1.48-1.75,11,11,0,0,0-21.72,0A1.5,1.5,0,0,0,2.62,12h0a1.53,1.53,0,0,0,1.49-1.3A8,8,0,0,1,12,4Z"
        >
          <animateTransform
            attributeName="transform"
            dur="0.75s"
            repeatCount="indefinite"
            type="rotate"
            values="0 12 12;360 12 12"
          />
        </path>
      </svg>
    </button>

    <div class="grid grid-cols-1 md:grid-cols-2 gap-5">
      <div
        v-for="(item, index) in tickets[0].detail"
        :key="index"
        class="bg-wite flex gap-3 flex-col"
      >
        <div class="flex bg-blue-500 text-white rounded-xl px-5 py-4">
          <div class="flex flex-col gap-2 text-xl">
            <p>if You Want to Go Far, Go Together</p>

            <div class="flex gap-2.5 items-center">
              <svg
                xmlns="http://www.w3.org/2000/svg"
                width="2rem"
                height="2rem"
                viewBox="0 0 256 256"
              >
                <path
                  fill="currentColor"
                  d="m221.59 160.3l-47.24-21.17a14 14 0 0 0-13.28 1.22a5 5 0 0 0-.56.42l-24.69 21a1.88 1.88 0 0 1-1.68.06c-15.87-7.66-32.31-24-40-39.65a1.91 1.91 0 0 1 0-1.68l21.07-25a6 6 0 0 0 .42-.58a14 14 0 0 0 1.12-13.27L95.73 34.49a14 14 0 0 0-14.56-8.38A54.24 54.24 0 0 0 34 80c0 78.3 63.7 142 142 142a54.25 54.25 0 0 0 53.89-47.17a14 14 0 0 0-8.3-14.53M176 210c-71.68 0-130-58.32-130-130a42.23 42.23 0 0 1 36.67-42h.23a2 2 0 0 1 1.84 1.31l21.1 47.11a2 2 0 0 1 0 1.67l-21.11 25.06a5 5 0 0 0-.43.57a14 14 0 0 0-.91 13.73c8.87 18.16 27.17 36.32 45.53 45.19a14 14 0 0 0 13.77-1c.19-.13.38-.27.56-.42l24.68-21a1.92 1.92 0 0 1 1.6-.1l47.25 21.17a2 2 0 0 1 1.21 2A42.24 42.24 0 0 1 176 210"
                />
              </svg>
              <span> +964 708 814 3063 </span>
            </div>
          </div>
        </div>

        <div class="border rounded-xl p-3 flex flex-col gap-4">
          <h3 class="text-xl font-bold">Ticket detail</h3>

          <div
            class="grid gap-x-10 md:grid-rows-4 md:grid-cols-2 text-gray-500"
          >
            <div class="flex justify-between">
              <span> Date of birth: </span>

              <span class="font-semibold"> {{ item.birth_date }} </span>
            </div>
            <div class="flex justify-between">
              <span> Expiration of passport: </span>

              <span class="font-semibold"> {{ item.deprecate_passport }} </span>
            </div>
            <div class="flex justify-between">
              <span> Ticket ID: </span>

              <span class="font-semibold"> 26521564515 </span>
            </div>
            <div class="flex justify-between">
              <span> Nationality: </span>

              <span class="font-semibold"> {{ item.national }} </span>
            </div>
            <div class="flex justify-between">
              <span> Gender: </span>

              <span class="font-semibold"> {{ item.gender }} </span>
            </div>
            <div class="flex justify-between">
              <span> PIS: </span>

              <span class="font-semibold"> {{ item.country }} </span>
            </div>
            <div class="flex justify-between">
              <span> First Name: </span>

              <span class="font-semibold"> {{ item.name }} </span>
            </div>
            <div class="flex justify-between">
              <span> Last Name: </span>

              <span class="font-semibold"> {{ item.last_name }} </span>
            </div>
            <div class="flex justify-between">
              <span> Passport Number: </span>

              <span class="font-semibold"> {{ item.number_passport }} </span>
            </div>
          </div>
        </div>

        <div class="flex items-center">
          <div
            class="bg-blue-500 flex flex-col justify-center gap-1 py-10 rounded-l-xl text-white text-xl font-bold"
          >
            <span class="-rotate-90">Flight</span>
            <span class="-rotate-90"> Go </span>
          </div>

          <div
            class="border bg-gray-50 rounded-r-xl py-3 px-5 w-full h-full flex justify-between flex-col"
          >
            <div class="flex items-center justify-between">
              <div class="flex items-center gap-2">
                <span class="text-gray-500"> Flight number: </span>

                <span class="font-medium"> 33255315645554 </span>
              </div>

              <span> economy </span>
            </div>

            <div class="flex justify-between">
              <div class="flex flex-col">
                <div class="flex items-center gap-2">
                  <span class="text-3xl font-bold">
                    {{
                      format({
                        date: tickets[1].ticket.outbound_group
                          .departure_date_time,
                        format: "HH:mm",
                        tz: "UTC",
                      })
                    }}
                  </span>
                  <span class="text-gray-500">
                    {{
                      format({
                        date: tickets[1].ticket.outbound_group
                          .departure_date_time,
                        format: "D/MMM/YYYY",
                        tz: "UTC",
                      })
                    }}
                  </span>
                </div>

                <p class="text-sm text-gray-500">
                  {{ tickets[2].origin }} - Imamkhomeini Airport (IMK)
                </p>
              </div>
              <div
                class="flex flex-col text-gray-500 items-center justify-center"
              >
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  width="1.5rem"
                  height="1.5rem"
                  viewBox="0 0 512 512"
                >
                  <path
                    fill="currentColor"
                    d="M407.72 208c-2.72 0-14.44.08-18.67.31l-57.77 1.52L198.06 48h-62.81l74.59 164.61l-97.31 1.44L68.25 160H16.14l20.61 94.18c.15.54.33 1.07.53 1.59a.26.26 0 0 1 0 .15a15 15 0 0 0-.53 1.58L15.86 352h51.78l45.45-55l96.77 2.17L135.24 464h63l133-161.75l57.77 1.54c4.29.23 16 .31 18.66.31c24.35 0 44.27-3.34 59.21-9.94C492.22 283 496 265.46 496 256c0-30.06-33-48-88.28-48m-71.29 87.9"
                  />
                </svg>

                <span class="text-sm"> nonstop </span>
              </div>
              <div class="flex flex-col">
                <div class="flex items-center gap-2">
                  <span class="text-gray-500">
                    {{
                      format({
                        date: tickets[1].ticket.outbound_group
                          .arrival_date_time,
                        format: "D/MMM/YYYY",
                        tz: "UTC",
                      })
                    }}
                  </span>
                  <span class="text-3xl font-bold">
                    {{
                      format({
                        date: tickets[1].ticket.outbound_group
                          .arrival_date_time,
                        format: "HH:mm",
                        tz: "UTC",
                      })
                    }}
                  </span>
                </div>

                <p class="text-sm text-gray-500">
                  {{ tickets[2].destination }} - Imamkhomeini Airport (IMK)
                </p>
              </div>
            </div>

            <div class="flex items-center text-sm justify-between">
              <div class="flex items-center gap-2">
                <span>
                  {{ tickets[2].destination }} Air - {{ tickets[2].origin }} Air
                </span>
              </div>

              <div class="flex items-center gap-2">
                <span
                  >Two packages ({{
                    tickets[1].ticket.outbound_group.flight_segments[0]
                      .baggage_kg
                  }}
                  kg each)</span
                >
                <svg
                  width="20"
                  height="20"
                  viewBox="0 0 24 24"
                  fill="none"
                  xmlns="http://www.w3.org/2000/svg"
                >
                  <path
                    d="M18 20V7C18 6.4477 17.5523 6 17 6H5C4.44771 6 4 6.4477 4 7V19C4 19.5523 4.44771 20 5 20H18Z"
                    stroke="#605D64"
                    stroke-width="2"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                  ></path>
                  <path
                    d="M8 6V20"
                    stroke="#605D64"
                    stroke-width="2"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                  ></path>
                  <path
                    d="M14 6V19"
                    stroke="#605D64"
                    stroke-width="2"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                  ></path>
                  <path
                    d="M14 6V3C14 2.44771 13.5523 2 13 2H9C8.4477 2 8 2.44771 8 3V6"
                    stroke="#605D64"
                    stroke-width="2"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                  ></path>
                  <path
                    d="M6.5 20V22"
                    stroke="#605D64"
                    stroke-width="2"
                    stroke-linecap="round"
                  ></path>
                  <path
                    d="M16 20V22"
                    stroke="#605D64"
                    stroke-width="2"
                    stroke-linecap="round"
                  ></path>
                </svg>
              </div>
            </div>
          </div>
        </div>

        <div class="border rounded-xl py-4 px-6 flex gap-5 flex-col">
          <div class="flex flex-col gap-2.5">
            <h3 class="font-bold text-xl">Important nots</h3>

            <p class="text-gray-500 text-sm">
              Lorem ipsum dolor sit amet consectetur adipisicing elit. Maxime
              mollitia, molestiae quas vel sint commodi repudiandae consequuntur
              voluptatum laborum numquam blanditiis harum quisquam eius sed odit
              fugiat iusto fuga praesentium optio, eaque rerum! Provident
              similique accusantium nemo autem. Veritatis obcaecati tenetur iure
              eius earum ut molestias architecto voluptate aliquam nihil,
              eveniet aliquid culpa officia aut! Impedit sit sunt quaerat, odit,
              tenetur error, harum nesciunt ipsum debitis quas aliquid.
              Reprehenderit, quia. Quo neque error repudiandae fuga? Ipsa
              laudantium molestias eos sapiente officiis modi at sunt excepturi
              expedita sint? Sed quibusdam recusandae alias error harum maxime
              adipisci amet laborum. Perspiciatis minima nesciunt dolorem!
              Officiis iure rerum voluptates a cumque velit
            </p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { format } from "@formkit/tempo";
const { tickets } = useTickets();
const loading = ref(false);
const basePdf = ref(null);

onMounted(async () => {
  try {
    loading.value = true;
    const data = await $fetch("/api/pdf/export-pdf", {
      method: "POST",
      body: {
        data: tickets.value[0].detail.map((i) => {
          i.flight_time = format({
            date: tickets.value[1].ticket.outbound_group.departure_date_time,
            format: "HH:mm A D MMMM",
            tz: "UTC",
          });

          i.arrival_date = format({
                        date: tickets.value[1].ticket.outbound_group
                          .arrival_date_time,
                          format: "D/MMM/YYYY",
                        tz: "UTC",
                      }),
          i.arrival_time =
                      format({
                        date: tickets.value[1].ticket.outbound_group
                          .arrival_date_time,
                        format: "HH:mm",
                        tz: "UTC",
                      }),
          i.departure_date = format({
                        date: tickets.value[1].ticket.outbound_group
                          .departure_date_time,
                          format: "D/MMM/YYYY",
                        tz: "UTC",
                      }),
          i.departure_time =
                      format({
                        date: tickets.value[1].ticket.outbound_group
                          .departure_date_time,
                        format: "HH:mm",
                        tz: "UTC",
                      }),
          i.stop_time = `${Math.floor(
            tickets.value[1].ticket.outbound_group.journey_duration_in_minute /
              60
          )}h ${Math.floor(
            tickets.value[1].ticket.outbound_group.journey_duration_in_minute %
              60
          )}m.`;
          i.time = format({
            date: tickets.value[1].ticket.outbound_group.departure_date_time,
            format: "HH:mm A",
            tz: "UTC",
          });
          i.date = format({
            date: tickets.value[1].ticket.outbound_group.departure_date_time,
            format: "D MMMM YYYY",
            tz: "UTC",
          });
          i.price = tickets.value[1].ticket.price_detail.total_fare.payable;
          i.baggage =
            tickets.value[1].ticket.outbound_group.flight_segments[0].baggage_kg;
          i.flight_number =
            tickets.value[1].ticket.outbound_operating_airlines[0].flight_number;
          i.issue_time = `${format({
            date: new Date(),
            format: "HH:mm A",
            tz: "UTC",
          })} , ${format({
            date: new Date(),
            format: "D MMMM YYYY",
            tz: "UTC",
          })}`;
          i.origin = tickets.value[2].origin;
          i.destination = tickets.value[2].destination;
          i.icon = tickets.value[2].icon;
          i.airline = tickets.value[2].airline;

          return i;
        }),
      },
    });

    basePdf.value = data;
  } catch (error) {
    console.error("Error render PDF:", error.message);
  } finally {
    loading.value = false;
  }
});

const downloadPdf = () => {
  const linkSource = `data:application/pdf;base64,${basePdf.value}`;
  const downloadLink = document.createElement("a");
  const fileName = "test.pdf";
  downloadLink.style.display = "hidden";
  downloadLink.href = linkSource;
  downloadLink.download = fileName;
  downloadLink.click();
};
</script>
